# OneTap Uploader — Android starter

This is a **UI prototype**, not a working social-media publisher yet.

## Open in Android Studio
1. Install Android Studio (stable version) and Android SDK Platform 35.
2. Extract this ZIP.
3. Android Studio → Open → select the `OneTapUploader` folder.
4. Allow Gradle sync and install any requested SDK components.
5. Connect an Android phone with USB debugging enabled, or start an emulator.
6. Press Run.

## Build an APK
Android Studio → Build → Build Bundle(s) / APK(s) → Build APK(s).
The debug APK is normally created at:
`app/build/outputs/apk/debug/app-debug.apk`

## Current prototype features
- Select a video using Android's system video picker.
- Select YouTube, Instagram and Facebook.
- Enter a title and caption.
- Basic validation and UI feedback.

## Not implemented yet
- OAuth sign-in / token refresh.
- YouTube upload API.
- Instagram Reels publishing.
- Facebook Reels publishing.
- Backend, secure token storage, upload queue, retry and status tracking.
- Scheduling.

Never put client secrets or long-lived access tokens in the Android app.
