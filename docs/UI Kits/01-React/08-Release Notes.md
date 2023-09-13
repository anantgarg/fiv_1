---
sidebar_position: 8
title: Release Notes
slug: /release-notes
---

## 2023

#### January, 30th

New Support for SDK v3.0.11

Bugfixes

1. Fixed the emoji cursor position on compose message and edit message
2. Fixed a bug to address scroll position to a particular category in the emoji keyboard
3. Fixed a bug in Emoji keyboard which caused the message composer to disappear under smaller resolution
4. Updated Twemoji cdn issue; using the new npm package twemoji/api
5. Fixed the Unread count update when scrolling to bottom of message list
6. Fixed the incorrect Group member count in group list

## 2022

#### August, 17th

v3.0.10-1

New Support for SDK v3.0.10

Bugfixes

1. Fixed React v18 compatibility there by removed third party package emoji-mart dependency

#### February, 9th

New Support for SDK v3.0.6

Improvements

1. Updated peer dependencies, replaced react-html-parser

Bugfixes

1. Blank screen in mobile resolution on user leaving the group
2. Mismatch in members count on user leaving a group or on kicked.

#### January, 10th

v3.0.5-1

New Support for SDK v3.0.5

Improvements 

1. Fixed an issue where CometChatMessages component crashed due to a run-time error
2. Improved Delivery and Read Receipts by adding error handling for CometChat.markAsRead and CometChat.markAsDelivered methods
3. Improvements in French Language Translations
4. Optimised real-time update in CometChatGroupList component for onMemberJoined and onMemberAdded listener events
5. Made improvements to the votes, now when the logged-in user votes in a poll, a tick with a blue background is shown to that user

## 2021

#### October, 19th

v3.0.2-beta1-1 

New Option to show call recording button for users to enable recording of voice and video calls

Improvement Correction of translations for Spanish language

#### October, 4th

3.0.1-2 

New Optimistic UI for message reactions

New UI indicating the user is blocked

New Localised strings for calling components

ImprovementBug fixes

---