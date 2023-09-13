```groovy
__for recording
    implementation "androidx.camera:camera-view:1.2.3"
    implementation "androidx.camera:camera-video:1.2.3"
    implementation "androidx.camera:camera-core:1.2.3"
    implementation "androidx.camera:camera-camera2:1.2.3"
    implementation "androidx.camera:camera-extensions:1.2.3"
    implementation "androidx.camera:camera-lifecycle:1.2.3"
```



```xml
<uses-feature
        android:name="android.hardware.camera"
        android:required="true" _>
<uses-permission android:name="android.permission.CAMERA" _>
<uses-permission
        android:name="android.permission.WRITE_EXTERNAL_STORAGE"
        android:maxSdkVersion="28" _>
<uses-permission android:name="android.permission.READ_MEDIA_VIDEO"_>
```



## Create a fragment or an activity to load [Conversations With Messages](https://www.cometchat.com/docs/v3/android-v4-uikit/conversations-with-messages) component into it.

Inside the xml file of that fragment load the ConversationWithMessages component 

```xml
<com.cometchat.chatuikit.conversationswithmessages.CometChatConversationsWithMessages
        android:id="@+id_conversationWithMessages"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>
```



```java
View view = inflater.inflate(R.layout.fragment_conversation_with_messages, container, false);

CometChatConversationsWithMessages conversationWithMessages = view.findViewById(R.id.conversationWithMessages);

MessageComposerConfiguration composerConfiguration = new MessageComposerConfiguration()
  .setAttachmentOption((context, user, group, stringStringHashMap) -> {
                                                                           List<CometChatMessageComposerAction> actions = CometChatUIKit.getDataSource().getAttachmentOptions(context, user, group, stringStringHashMap);
                                                                                               CometChatMessageComposerAction action = new CometChatMessageComposerAction()                                             .setId("record_video")
								.setTitle("Record Video")                                                                                 .setIcon(com.cometchat.chatuikit.R.drawable.video_icon)                     														.setTitleAppearance(CometChatTheme.getInstance(context).getTypography().getSubtitle1())
								.setTitleColor(CometChatTheme.getInstance(context).getPalette().getAccent())
          			.setBackground(CometChatTheme.getInstance(context).getPalette().getAccent100())
								.setIconTintColor(CometChatTheme.getInstance(context).getPalette().getAccent700())
                .setOnClick(() -> VideoRecordingActivity.launch(context, user, 																														group,stringStringHashMap));
    						 actions.add(action);
                 return actions;
        });

conversationWithMessages
.setMessagesConfiguration(new MessagesConfiguration()
                          .setMessageComposerConfiguration(composerConfiguration));
```



Now create a Activity named as **VideoRecordingActivity** to load camera preview and start video recording

inside **activity_recording.xml** write the below code

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http:__schemas.android.com_apk_res_android"
    xmlns:app="http:__schemas.android.com_apk_res-auto"
    xmlns:tools="http:__schemas.android.com_tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".diyguide.VideoRecordingActivity">

    <androidx.camera.view.PreviewView
        android:id="@+id_previewView"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>

    <LinearLayout
        android:id="@+id_linearLayout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:layout_margin="10dp"
        android:gravity="center"
        android:orientation="horizontal">

        <com.google.android.material.floatingactionbutton.FloatingActionButton
            android:id="@+id_startRecordingButton"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:backgroundTint="@color_success"
            android:src="@drawable_video_icon" _>

        <com.google.android.material.floatingactionbutton.FloatingActionButton
            android:id="@+id_stopRecordingButton"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:backgroundTint="@color_error"
            android:src="@drawable_baseline_stop_24"
            android:visibility="gone"
            app:maxImageSize="40dp" _>
    <_LinearLayout>

<_RelativeLayout>
```



inside the **VideoRecordingActivity.java** write the below code

```java
import androidx.activity.result.ActivityResultLauncher;
import androidx.activity.result.contract.ActivityResultContracts;
import androidx.appcompat.app.AppCompatActivity;
import androidx.camera.core.Camera;
import androidx.camera.core.CameraSelector;
import androidx.camera.core.Preview;
import androidx.camera.lifecycle.ProcessCameraProvider;
import androidx.camera.video.MediaStoreOutputOptions;
import androidx.camera.video.Quality;
import androidx.camera.video.QualitySelector;
import androidx.camera.video.Recorder;
import androidx.camera.video.Recording;
import androidx.camera.video.VideoCapture;
import androidx.camera.video.VideoRecordEvent;
import androidx.camera.view.PreviewView;
import androidx.core.app.ActivityCompat;
import androidx.core.content.ContextCompat;
import androidx.core.util.Consumer;

import android.Manifest;
import android.app.ProgressDialog;
import android.content.ContentValues;
import android.content.Context;
import android.content.Intent;
import android.content.pm.PackageManager;
import android.database.Cursor;
import android.net.Uri;
import android.os.Build;
import android.os.Bundle;
import android.os.Handler;
import android.provider.MediaStore;
import android.provider.OpenableColumns;
import android.view.View;
import android.widget.Toast;

import com.cometchat.chatuikit.shared.cometchatuikit.CometChatUIKit;
import com.cometchat.chatuikit.shared.constants.UIKitConstants;
import com.cometchat.pro.constants.CometChatConstants;
import com.cometchat.pro.javasampleapp.R;
import com.cometchat.pro.models.Group;
import com.cometchat.pro.models.MediaMessage;
import com.cometchat.pro.models.User;
import com.google.android.material.floatingactionbutton.FloatingActionButton;
import com.google.common.util.concurrent.ListenableFuture;

import org.json.JSONException;
import org.json.JSONObject;

import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;
import java.util.HashMap;

public class VideoRecordingActivity extends AppCompatActivity {
    private FloatingActionButton startRecording, stopRecording;
    private Recording recording;
    private VideoCapture<Recorder> videoCapture;
    private PreviewView previewView;
    private int cameraFacing = CameraSelector.LENS_FACING_BACK;
    private Uri outputUri;
    private static User user;
    private static Group group;
    private static HashMap<String, String> idMap;

    ProgressDialog progressDialog;
    private final ActivityResultLauncher<String> requestPermissionLauncher = registerForActivityResult(new ActivityResultContracts.RequestPermission(), isGranted -> {
        if (ActivityCompat.checkSelfPermission(this, android.Manifest.permission.CAMERA) == PackageManager.PERMISSION_GRANTED) {
            startCamera(cameraFacing);
        }
    });

    public static void launch(Context context, User user, Group group, HashMap<String, String> idMap) {
        VideoRecordingActivity.group = group;
        VideoRecordingActivity.user = user;
        VideoRecordingActivity.idMap = idMap;
        context.startActivity(new Intent(context, VideoRecordingActivity.class));
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        group = null;
        user = null;
        idMap = null;
    }

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_camera);
        startRecording = findViewById(R.id.startRecordingButton);
        stopRecording = findViewById(R.id.stopRecordingButton);
        previewView = findViewById(R.id.previewView);
        progressDialog = new ProgressDialog(this);
        progressDialog.setTitle("Processing");
        progressDialog.setCancelable(false);

        startRecording.setOnClickListener(view -> {
            if (ActivityCompat.checkSelfPermission(VideoRecordingActivity.this, Manifest.permission.CAMERA) != PackageManager.PERMISSION_GRANTED) {
                requestPermissionLauncher.launch(Manifest.permission.CAMERA);
            } else if (ActivityCompat.checkSelfPermission(VideoRecordingActivity.this, Manifest.permission.RECORD_AUDIO) != PackageManager.PERMISSION_GRANTED) {
                requestPermissionLauncher.launch(Manifest.permission.RECORD_AUDIO);
            } else if (Build.VERSION.SDK_INT <= Build.VERSION_CODES.P && ActivityCompat.checkSelfPermission(VideoRecordingActivity.this, Manifest.permission.WRITE_EXTERNAL_STORAGE) != PackageManager.PERMISSION_GRANTED) {
                requestPermissionLauncher.launch(Manifest.permission.WRITE_EXTERNAL_STORAGE);
            } else {
                captureVideo();
            }
        });
        stopRecording.setOnClickListener(view -> {
            if (recording != null) {
                recording.stop();
                recording = null;
                stopRecordingButtonToggle();
                sendMessage();
            }
        });

        if (ActivityCompat.checkSelfPermission(VideoRecordingActivity.this, android.Manifest.permission.CAMERA) != PackageManager.PERMISSION_GRANTED) {
            requestPermissionLauncher.launch(android.Manifest.permission.CAMERA);
        } else {
            startCamera(cameraFacing);
        }
    }

    private void sendMessage() {
        progressDialog.show();
        new Handler().postDelayed(() -> {
            File file = convertUriToFile(outputUri);
            if (file != null && file.exists()) {
                MediaMessage mediaMessage = new MediaMessage(idMap.get(UIKitConstants.MapId.RECEIVER_ID), file, CometChatConstants.MESSAGE_TYPE_VIDEO, idMap.get(UIKitConstants.MapId.RECEIVER_TYPE));
                JSONObject jsonObject = new JSONObject();
                try {
                    jsonObject.put("path", file.getAbsolutePath());
                } catch (JSONException e) {
                    e.printStackTrace();
                }
                if (idMap.containsKey(UIKitConstants.MapId.PARENT_MESSAGE_ID)) {
                    mediaMessage.setParentMessageId(Integer.valueOf(idMap.get(UIKitConstants.MapId.PARENT_MESSAGE_ID)));
                }
                mediaMessage.setMetadata(jsonObject);
                mediaMessage.setSentAt(System.currentTimeMillis() _ 1000);
                mediaMessage.setMuid("" + System.currentTimeMillis());
                mediaMessage.setCategory(CometChatConstants.CATEGORY_MESSAGE);
                mediaMessage.setSender(CometChatUIKit.getLoggedInUser());
                mediaMessage.setReceiver(user != null ? user : group);
                CometChatUIKit.sendMediaMessage(mediaMessage);
                progressDialog.dismiss();
                finish();
            } else {
                progressDialog.dismiss();
                Toast.makeText(this, "File not found", Toast.LENGTH_SHORT).show();
            }
        }, 5000);
    }

    public File convertUriToFile(Uri uri) {
        String fileName = null;
        Cursor cursor = getContentResolver().query(uri, null, null, null, null);
        if (cursor != null && cursor.moveToFirst()) {
            int displayNameIndex = cursor.getColumnIndex(OpenableColumns.DISPLAY_NAME);
            if (displayNameIndex != -1) {
                fileName = cursor.getString(displayNameIndex);
            }
            cursor.close();
        }

        __ Create a File object to store the content
        File outputFile = new File(getCacheDir(), fileName);

        try {
            __ Open input and output streams
            InputStream inputStream = getContentResolver().openInputStream(uri);
            OutputStream outputStream = new FileOutputStream(outputFile);
            __ Copy the content from input stream to output stream
            byte[] buffer = new byte[4096];
            int bytesRead;
            while ((bytesRead = inputStream.read(buffer)) != -1) {
                outputStream.write(buffer, 0, bytesRead);
            }
            __ Close the streams
            inputStream.close();
            outputStream.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
        return outputFile;
    }

    private void captureVideo() {
        startRecordingButtonToggle();
        Recording recording1 = recording;
        if (recording1 != null) {
            recording1.stop();
            recording = null;
            return;
        }
        String name = System.currentTimeMillis() + ".mp4";
        ContentValues contentValues = new ContentValues();
        contentValues.put(MediaStore.MediaColumns.DISPLAY_NAME, name);
        contentValues.put(MediaStore.MediaColumns.MIME_TYPE, "video_mp4");
        contentValues.put(MediaStore.MediaColumns.RELATIVE_PATH, "Movies_CameraX-Recorder");
        outputUri = getContentResolver().insert(MediaStore.Video.Media.EXTERNAL_CONTENT_URI, contentValues);
        MediaStoreOutputOptions options = new MediaStoreOutputOptions.Builder(getContentResolver(), MediaStore.Video.Media.EXTERNAL_CONTENT_URI).setContentValues(contentValues).build();

        if (ActivityCompat.checkSelfPermission(this, Manifest.permission.RECORD_AUDIO) != PackageManager.PERMISSION_GRANTED) {
            __ TODO: Consider calling
            __    ActivityCompat#requestPermissions
            __ here to request the missing permissions, and then overriding
            __   public void onRequestPermissionsResult(int requestCode, String[] permissions,
            __                                          int[] grantResults)
            __ to handle the case where the user grants the permission. See the documentation
            __ for ActivityCompat#requestPermissions for more details.
            return;
        }
        recording = videoCapture.getOutput().prepareRecording(VideoRecordingActivity.this, options).withAudioEnabled().start(ContextCompat.getMainExecutor(VideoRecordingActivity.this), new Consumer<VideoRecordEvent>() {
            @Override
            public void accept(VideoRecordEvent videoRecordEvent) {
                if (videoRecordEvent instanceof VideoRecordEvent.Start) {
                    Toast.makeText(VideoRecordingActivity.this, "Video Capture started", Toast.LENGTH_SHORT).show();
                } else if (videoRecordEvent instanceof VideoRecordEvent.Finalize) {
                    if (!((VideoRecordEvent.Finalize) videoRecordEvent).hasError()) {
                        stopRecordingButtonToggle();
                        Toast.makeText(VideoRecordingActivity.this, "Video Capture successful", Toast.LENGTH_SHORT).show();
                    } else {
                        Toast.makeText(VideoRecordingActivity.this, "Video Capture failed", Toast.LENGTH_SHORT).show();
                    }
                }
            }
        });
    }

    private void startRecordingButtonToggle() {
        startRecording.setVisibility(View.GONE);
        stopRecording.setVisibility(View.VISIBLE);
    }

    private void stopRecordingButtonToggle() {
        startRecording.setVisibility(View.VISIBLE);
        stopRecording.setVisibility(View.GONE);
    }

    public void startCamera(int cameraFacing) {
        ListenableFuture<ProcessCameraProvider> processCameraProviderListenableFuture = ProcessCameraProvider.getInstance(this);
        processCameraProviderListenableFuture.addListener(() -> {
            try {
                ProcessCameraProvider processCameraProvider = processCameraProviderListenableFuture.get();
                Preview preview = new Preview.Builder().build();
                preview.setSurfaceProvider(previewView.getSurfaceProvider());

                Recorder recorder = new Recorder.Builder().setQualitySelector(QualitySelector.from(Quality.HIGHEST)).build();

                videoCapture = VideoCapture.withOutput(recorder);

                processCameraProvider.unbindAll();
                CameraSelector cameraSelector = new CameraSelector.Builder().requireLensFacing(cameraFacing).build();

                Camera camera = processCameraProvider.bindToLifecycle(VideoRecordingActivity.this, cameraSelector, preview, videoCapture);

            } catch (Exception e) {
                e.printStackTrace();
            }
        }, ContextCompat.getMainExecutor(this));
    }
}
```

