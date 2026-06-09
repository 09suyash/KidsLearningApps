# 🎓 Kids Learning Apps — Android Project

A native Android app that packages 3 educational HTML apps in a full-screen WebView.

---

## 📱 What's Inside

| App | Description |
|-----|-------------|
| 🔤 ABC & Phonics Pro | Learn 26 letters, voice, tracing canvas, quiz |
| 🔢 Math Quiz Pro | Practice, Times Tables, 60-second Blitz mode |
| 📚 Moral Stories | 8 stories in Hindi + English with voice narration |

---

## 🛠️ How to Build the APK (5 minutes)

### Step 1 — Install Android Studio
Download from: https://developer.android.com/studio

### Step 2 — Open Project
1. Open Android Studio
2. Click **File → Open**
3. Select this folder (KidsLearningApps)
4. Wait for Gradle sync to complete (~1-2 min)

### Step 3 — Build Debug APK (for testing)
1. Click **Build → Build Bundle(s) / APK(s) → Build APK(s)**
2. Wait ~1-2 minutes
3. Click "locate" in the notification bar
4. APK is at: `app/build/outputs/apk/debug/app-debug.apk`

### Step 4 — Install on Phone
1. Enable **Developer Mode** on your Android phone:
   - Settings → About Phone → tap "Build Number" 7 times
2. Enable **USB Debugging**: Settings → Developer Options → USB Debugging
3. Connect phone via USB
4. In Android Studio: **Run → Run 'app'** (Shift+F10)

**OR** copy the APK file to your phone and tap it to install.

---

## 💰 How to Add AdMob Ads

### Step 1 — Create AdMob Account
Go to https://admob.google.com and create an app

### Step 2 — Get Your IDs
- App ID: `ca-app-pub-XXXXXXXXXXXXXXXX~XXXXXXXXXX`
- Ad Unit ID (Banner): `ca-app-pub-XXXXXXXXXXXXXXXX/XXXXXXXXXX`

### Step 3 — Enable in Code

**In `app/build.gradle`** — uncomment this line:
```gradle
implementation 'com.google.android.gms:play-services-ads:23.0.0'
```

**In `AndroidManifest.xml`** — add inside `<application>`:
```xml
<meta-data
    android:name="com.google.android.gms.ads.APPLICATION_ID"
    android:value="ca-app-pub-XXXXXXXXXXXXXXXX~XXXXXXXXXX"/>
```

**In `MainActivity.java`** — add in `onCreate()`:
```java
MobileAds.initialize(this, initializationStatus -> {});
AdView adView = new AdView(this);
adView.setAdSize(AdSize.BANNER);
adView.setAdUnitId("ca-app-pub-XXXXXXXXXXXXXXXX/XXXXXXXXXX");
// Add adView to a LinearLayout at the bottom
AdRequest adRequest = new AdRequest.Builder().build();
adView.loadAd(adRequest);
```

---

## 📦 Build Release APK (for Play Store)

1. **Build → Generate Signed Bundle/APK**
2. Choose **APK**
3. Create a new keystore (save it safely!)
4. Build **release** variant
5. APK at: `app/build/outputs/apk/release/app-release.apk`

---

## 📋 App Details

- **Package**: `com.kidslearning.apps`
- **Min Android**: 7.0 (API 24) — covers 95%+ of phones
- **Target Android**: 14 (API 34)
- **Permissions**: Internet only (for Google Fonts)
- **Size**: ~1.5 MB (all HTML, no large resources)

---

## 🔧 Customization

To change the **package name** for Play Store:
1. `app/build.gradle` → change `applicationId`
2. Right-click `com.kidslearning` folder → Refactor → Rename

To add **more HTML apps**:
1. Place `.html` file in `app/src/main/assets/www/`
2. Add a card in `index.html`

