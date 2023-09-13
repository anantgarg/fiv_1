CometChat UI Kit has dependancy on CometChat SDK which communicates directly with Rest API server. Client

application uses the elements or the UI components provided by the UI Kit.

![](https://uploads.developerhub.io/prod/x9W8/barmv7hyu4t869zkyhmzsfebb0xdww2ul6x54vqe1coy4wunl5vy1dh9g7035g5c.png)

---

## SDK

CometChat SDK manages chat data while communicating with Rest API Server. It sends an events to the UI Kit whenever there is updates on to the data.

![](https://uploads.developerhub.io/prod/x9W8/h0glwlmtoi9bfscyydqmq8bu0913koqsss1ckwln3mtcckpfcog5u807o7jhay0i.png)

---

## UIKit

CometChat UIKit triggers CometChat SDK interfaces when the user interaction has occured or other circumstances.

When CometChat SDK sends events to UIKit, UIKit components updates views with received data through events.

![](https://uploads.developerhub.io/prod/x9W8/n05fitbf1xv58kvpbzeaipi2da9ia2ies4bir40jvkdi3lv3b6xijakqddjcczpp.png)