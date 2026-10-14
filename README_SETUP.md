# Discipline Focus Assistant - Flutter Android Setup Guide

A production-ready Flutter Android application for mobile discipline:
- **Morning Alarm System**: Loud alarm with vibration and speech-to-text verification ("Ami ghum theke uthechi").
- **Focus/Study Mode**: Mandatory live desk camera snapshot before activating focus timer.
- **App & Web Blocker**: Accessibility Service blocks Facebook, Instagram, YouTube Shorts, and adult domains.
- **Allowed Whitelist**: Keeps WhatsApp, Gmail, and phone calls accessible.

---

## 🚀 Step 1: Create the Flutter Project
Open your terminal and run:
```bash
flutter create discipline_focus_assistant
cd discipline_focus_assistant
```

## 📦 Step 2: Add Required Dependencies
Update `pubspec.yaml` with the contents in the explorer, or run:
```bash
flutter pub add speech_to_text camera vibration flutter_ringtone_player shared_preferences permission_handler intl audioplayers
```

## ⚙️ Step 3: Configure Android Permissions & Accessibility
1. Copy the `android/app/src/main/AndroidManifest.xml` from this repository to your project.
2. Create `android/app/src/main/res/xml/accessibility_service_config.xml` with the service config.
3. Place `DisciplineAccessibilityService.kt` inside your Kotlin package directory:
   `android/app/src/main/kotlin/com/example/discipline_focus_assistant/`

## 📱 Step 4: Run on Physical Android Phone
1. Connect your Android phone with **USB Debugging** enabled in Developer Options.
2. Run:
   ```bash
   flutter run -d <your-device-id>
   ```

## 🔑 Step 5: Grant Required Android Permissions On Device
Once installed, grant these 2 permissions in Android Settings:
1. **Accessibility**: Go to `Settings > Accessibility > Installed Apps > Discipline Focus Assistant > Turn ON`. This allows real-time foreground app & web blocker.
2. **Display Over Other Apps**: Go to `Settings > Apps > Special App Access > Display Over Other Apps > Allow`.
3. **Camera & Microphone**: Allowed when prompted in app for desk capture & speech verification.

## 🗣️ Voice Wake-up Phrase
When the alarm rings in the morning:
- Say: **"Ami ghum theke uthechi"** (or in Bengali: **"আমি ঘুম থেকে উঠেছি"**).
- The Speech-to-Text engine parses the speech stream and dismisses the loud alarm once verified!
