# How to Update the App

## Updating HTML content (most common)
Edit any of these files:
- `app/src/main/assets/www/app1-abc.html` — ABC Phonics app
- `app/src/main/assets/www/app2-math.html` — Math Quiz app
- `app/src/main/assets/www/app3-stories.html` — Moral Stories app
- `app/src/main/assets/www/index.html` — Home screen / launcher

Then push to GitHub → new APK builds automatically in ~5 min.

## Releasing an update (Play Store)
Before each new release, bump the version in `app/build.gradle`:
```gradle
versionCode 2        ← increase by 1 each release
versionName "1.1.0"  ← change to new version string
```

## Adding a new story / subject
1. Create `app/src/main/assets/www/app4-newapp.html`
2. Add a new card in `index.html` pointing to it
3. Add a nav button in the bottom nav
4. Push → auto-build → new APK!

