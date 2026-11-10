# Phone se OneTap Uploader APK banana

## Aapko chahiye
- Android phone aur Chrome
- Internet
- Free GitHub account

## 1. GitHub account aur repository
1. Chrome me https://github.com kholen aur sign in / free sign up karein.
2. `New repository` banayein, naam `OneTapUploader` rakhein.
3. Repository ko Public ya Private rakh sakte hain.

## 2. Project files upload
1. Is ZIP ko phone ke File Manager me extract karein.
2. GitHub repository me `Add file` → `Upload files` kholen.
3. Extracted project ke andar ki files aur folders repository ke root me upload karein.
4. Hidden `.github/workflows/android.yml` file bhi upload karna zaroori hai. Agar phone ka file picker hidden folders nahi dikhata, to repository me `Add file` → `Create new file` karke path `.github/workflows/android.yml` banayein aur project ZIP ke andar wali workflow file ka content paste karein.
5. Commit changes karein.

Repository ke root par `settings.gradle.kts`, `build.gradle.kts`, `gradle.properties`, `app/` aur `.github/workflows/android.yml` hone chahiye.

## 3. APK build
1. Repository me `Actions` tab kholen.
2. `Build OneTap Uploader APK` workflow select karein.
3. `Run workflow` tap karein.
4. Build complete hone par run kholen → `Artifacts` → `OneTapUploader-debug-apk` download karein.
5. ZIP artifact extract karke `app-debug.apk` install karein.

Agar build fail ho, Actions run ka error screenshot bhejein; uske hisaab se fix karenge.

## Important limitations
- GitHub Actions ki free usage limits hoti hain; public repositories aur private repositories ke limits alag ho sakte hain.
- Ye APK abhi UI prototype hai. Actual publishing ke liye OAuth login, secure backend, platform API permissions aur testing abhi implement karni baaki hai.
- Social account passwords kabhi app ya chat me share na karein.
