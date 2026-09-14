# TIKTOD V3 — Android

Android port of the TIKTOD V3 engagement engine.

Multi-mode (Views / Hearts / Shares / Favorites / Followers) • OkHttp 4.12 pool • Proxy auth • Direct multi-path hits • Foreground service • Material dark UI.

**GitHub Actions builds the APK on every push.**

---

## Features

- **5 engagement modes** — Views, Hearts, Shares, Favorites, Followers
- **Dual connection** — Direct or Proxy (authenticated)
- **OkHttp 4.12** — 64-connection pool, keep-alive, reuse
- **Proxy formats** — `host:port` · `user:pass@host:port` · `user:pass:host:port`
- **Thread pool** — 4–64 workers
- **Jittered delay** — SeekBar 40–400 ms
- **Live stats** — sent / target, req/s, success %, progress bar
- **WakeLock + Foreground Service** — survives screen-off
- **Randomized UAs** — TikTok app + Chrome mobile

---

## Quick Start (no local SDK)

1. Push this repo to `main`
2. Open **Actions** → wait for green check
3. Download artifact **TiktodV3-Debug-APK**
4. Install on device → grant network permission → run

```bash
git clone https://github.com/yosefbatru-cmd/tiktod-v3-android.git
cd tiktod-v3-android
```

---

## Build locally (Android Studio)

1. Open the project folder
2. Sync Gradle
3. Build → Build APK(s)
4. Output: `app/build/outputs/apk/debug/app-debug.apk`

---

## Proxy formats

```
1.2.3.4:8080
user:pass@5.6.7.8:3128
user:pass:9.10.11.12:8000
```

One per line. Lines starting with `#` are ignored.

---

## Project layout

```
tiktod-v3-android/
├── app/
│   ├── build.gradle
│   ├── proguard-rules.pro
│   └── src/main/
│       ├── AndroidManifest.xml
│       ├── java/com/axion/tiktodv3/
│       │   ├── MainActivity.java
│       │   └── EngineService.java
│       └── res/
│           ├── layout/activity_main.xml
│           ├── values/
│           ├── drawable/
│           └── xml/network_security_config.xml
├── .github/workflows/build-apk.yml
├── build.gradle
├── settings.gradle
└── README.md
```

---

## Notes

- Min SDK 24 · Target SDK 34 · Java 17
- Replace live endpoints inside `sendHit()` paths if you wire a backend
- Built for Axion

**TIKTOD V3 Android — 3.0.0**
