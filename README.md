# TOKEN//TUMBLE

A roguelike slot compiler about AI tokens, broken synergies, and impossible project deadlines.
By **Fun Pixel x Panic Protocol**.

- Play in the browser: https://tokentumble.orivael.dev/
- Android APK: see the latest GitHub Release, or https://tokentumble.orivael.dev/token-tumble.apk

## v1.1 changes
- **Variable bet.** Raise or lower your bet each spin with `-` / `+` / `MAX` (or the Up/Down arrow keys). The bet can never go below the stage's base spin cost and is capped at 4x extra or your wallet. Payouts, bug faults and thermal crashes all scale with the bet multiplier.
- **Mobile and small screens.** Larger touch targets and readable text on phones, safe-area insets, `100dvh`, and a compact landscape layout.
- Branding: Fun Pixel x Panic Protocol.

## Layout
- `dist/` - the built web game (what the site and the APK serve)
- `android/` - Capacitor Android project (`com.panicprotocol.tokentumble`)

> The original TypeScript source was not available when v1.1 was made. v1.1 patches the built bundle in `dist/assets/` directly. The bet logic lives in the `OA` engine class (`betTotal`, `betMax`, `betMult`, `setBet`).

## Build the APK
Requires Node 18+, a JDK 17+ (Android Studio's bundled JBR works) and the Android SDK.

```
npm install
npx cap sync android
# release signing is optional; without these env vars the release APK is unsigned
set TT_KEYSTORE=path\to\your.jks & set TT_KEYPASS=yourpass   (key alias: tokentumble)
cd android && gradlew.bat assembleRelease
```
Output: `android/app/build/outputs/apk/release/app-release.apk`. For a quick test APK use `gradlew.bat assembleDebug`.
