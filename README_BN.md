# JARVIS Android Starter (v0.1)

এটি একটি প্রাথমিক Android Studio/Gradle project। GitHub Actions দিয়ে ফোন থেকেই APK build করা যাবে।

## এই ভার্সনে যা কাজ করে
- Futuristic dark JARVIS home screen
- Tap-to-speak microphone flow (Android SpeechRecognizer)
- বাংলা speech recognition locale request (`bn-IN`; ডিভাইসের speech service সমর্থন করতে হবে)
- Android Text-to-Speech response (pitch/rate কমানো হয়েছে; আসল deep voice engine/installed voice-এর উপর নির্ভরশীল)
- YouTube, WhatsApp, Instagram এবং custom website খোলা
- Add Apps dialog-এ website suggestions ও custom URL যোগ করা

## এখনো যা নেই
- Always-on “Jarvis” wake word
- OpenJarvis/cloud AI backend
- Offline LLM
- Background microphone foreground service

এসব ইচ্ছাকৃতভাবে পরের ধাপে যোগ হবে। এই starter-এ microphone শুধু ব্যবহারকারী mic button চাপলে চালু হয়। Android background microphone ব্যবহারে foreground service, notification, runtime permission এবং OS বিধিনিষেধ মানতে হয়।

## ফোন থেকেই APK build
1. GitHub-এ sign in করে নতুন **public বা private repository** তৈরি করো; নাম `JarvisAndroid` রাখতে পারো।
2. এই ZIP extract করে এর ভেতরের সব ফাইল repository-র root-এ upload করো (ফোল্ডারসহ)।
3. GitHub repository-তে **Actions** tab খোলো।
4. `Build Jarvis APK` workflow বেছে নিয়ে **Run workflow** চাপো। অথবা `main` branch-এ ফাইল push করলেই workflow চলবে।
5. Run শেষ হলে workflow run-এর নিচে **Artifacts → jarvis-debug-apk** থেকে APK download করো।
6. ZIP extract করে `app-debug.apk` install করো। Android চাইলে browser/file manager-এর জন্য “Install unknown apps” অনুমতি দিতে হবে।

## Wake word পরের ধাপে
Picovoice Porcupine Android SDK যোগ করা হবে। এর জন্য Picovoice Console থেকে AccessKey লাগবে। AccessKey কখনো public GitHub repository-তে commit করবে না; GitHub Actions Secrets বা secure local config ব্যবহার করতে হবে।

Official docs:
- https://picovoice.ai/docs/quick-start/porcupine-android/
- https://console.picovoice.ai/

## Project notes
- Package: `com.example.jarvis`
- Min Android API: 26
- Target/Compile SDK: 35
- Java: 17
- Gradle: 8.11.1
