# IV Launcher (all phases)

Pixel 11 के लिए आपका अपना launcher। ये Kotlin + Jetpack Compose में बना है और Android 12+ पर चलता है।

## क्या-क्या है
**Home & theme**
- Mixed grid: छोटे, Wide (2×1) और Big (2×2) icons। Page भरते ही अगला page अपने आप बनता है।
- Dock (4 fixed apps), Search pill, ✦ Gemini button, swipe-up app drawer
- Notification number badges
- 7 presets (Dark, AMOLED, Light, Glass, **Plush felt**, Gradient Night, Original) और हर चीज़ customizable

**Widgets** (IV Settings → Widgets, या home पर खाली जगह long-press)
- Tall clock, 7 styles: Tall thin, Stacked, Outline, Gradient, Glass, Split, Minimal। Height, width, weight और font सब बदल सकते हो।
- Weather (Open-Meteo, बिना API key), Calendar, Music (जो भी चल रहा हो)
- Custom app widget: कोई भी app, बड़ा emoji या icon, अपना text, अपने colors
- **Android widgets:** Gemini (Live के साथ), Google search, Spotify… 

**Gestures & overlays** (इनके लिए IV Helper चाहिए)
- **Arc picker:** home पर bottom-right edge दबाकर रखो → ऊपर-नीचे slide करो → उंगली छोड़ो → app खुल जाएगा
- Double-tap करके lock, swipe down करके notifications (आप बदल सकते हो)
- **Top pill:** camera के आस-पास call, recording, timer और music, साथ में काम करने वाले buttons
- **Camera decor:** camera के चारों तरफ़ ring (5 styles) और अपने stickers या GIFs, जिन्हें drag करके जगह पर रख सकते हो

**Status bar, voice & Google apps**
- **IV status bar** (home पर): time, date, notification वाले apps, 5G/4G, signal, Wi-Fi और battery, नए design में
- **IV Voice + Commands** (offline): home पर **खाली जगह एक tap** करो और बोलो, जैसे "Pixel, call Papa on speaker", "torch on", "alarm 6:30 am", "timer 5 minutes", "message Mom saying on my way", "open YouTube"। चाहो तो command type भी कर सकते हो। IV Settings → Voice में **अपनी commands** बनाओ (phrase → action)
- **☰ All features (side menu):** IV Settings में ऊपर बाईं तरफ़ ☰ दबाओ। हर feature, उसका battery खर्च और on/off switch एक जगह मिलेगा, साथ में एक-tap **Battery Saver**
- **Google apps के साथ पूरी compatibility:** Chrome/Maps/Contacts का "Add to home screen", Google और दूसरे apps के widgets, और long-press पर app shortcuts

**Lock screen & calls**
- **IV Lock Screen** (live wallpaper): tall clock, date + weather, battery, music, to-do, depth PNG layer
- **Call screen:** नाम, Message, Remind Me, slide to answer। **Volume Up दबाने से call कट जाएगी।** Outgoing screen भी है।
- सारे features **default में ON** रहते हैं। IV Settings में जाकर जो नहीं चाहिए उसे off कर दो।

## Install कैसे करें (Android Studio)
1. इस folder को **Android Studio** में खोलें (File → Open → `IVLauncher`)। पहली बार Gradle sync में कुछ मिनट लगेंगे।
2. Pixel 11 पर **Developer options → USB debugging** on करें और phone को USB से जोड़ें (या Wireless debugging use करें)।
3. ऊपर ▶ **Run** दबाएँ। Phone पर **IV Settings** खुलेगा।
4. ऊपर दिख रहे banner **"IV Launcher is not your Home app yet"** पर tap करें, फिर **IV Launcher** चुनें।
5. Home button दबाएँ। आपका नया home screen आ जाएगा 🎉
6. IV Settings → **Permissions** tab खोलें, फिर:
   - **Notification access:** badges, music, pill और call screen के लिए
   - **IV Helper (accessibility):** gestures, pill, camera decor और call screen के लिए (Settings → Accessibility → Downloaded apps → IV Helper)
   - **Location:** weather के लिए। **Phone, SMS और Notifications:** call screen के लिए
7. Lock screen के लिए: IV Settings → **Lock Screen** → *Apply IV lock screen* → Set wallpaper
8. सब हो जाने के बाद **USB debugging off** कर दें, ताकि बैंक और UPI apps बिना दिक्कत चलें।

> APK file बनाकर दोस्तों को देनी हो: **Build → Build App Bundle(s) / APK(s) → Build APK(s)**।
> APK से install करने पर Android 13+ notification access पर **"Restricted setting"** दिखा सकता है।
> तब: Settings → Apps → IV Settings → ⋮ (ऊपर दाईं तरफ़) → **Allow restricted settings**।
> Android Studio के ▶ Run से install करने पर ये दिक्कत नहीं आती।

## इस्तेमाल कैसे करें
| काम | कैसे |
|---|---|
| सारे apps देखना | Home पर ऊपर swipe करें |
| App को home पर लाना | Drawer में app को long-press करें → *Add to home screen* |
| Icon बड़ा या wide करना | Home पर app को long-press करें → *Small / Wide 2×1 / Big 2×2* |
| Icon आगे-पीछे करना | Long-press → *Move earlier / Move later* |
| Dock बदलना | Long-press → *Add to dock / Remove from dock* |
| किसी एक app का badge बंद करना | Long-press → *Hide badge for this app* |
| Settings खोलना | Home पर खाली जगह long-press करें → *IV Settings* |

## Uninstall / Pixel Launcher पर वापस जाना
- **Settings → Apps → Default apps → Home app → Pixel Launcher** चुन लें, या
- IV Settings → **More → Uninstall IV Launcher**। Android अपने आप Pixel Launcher पर लौट जाता है।
- कुछ भी permanent नहीं बदलता। Root की कोई ज़रूरत नहीं है।

## Limitations (Android की तरफ़ से)
- **Blur / glass** असली blur तभी देता है जब background picture IV के अंदर से चुनी गई हो।
- **Badge number** notifications से गिना जाता है। Notification clear करने पर number भी हट जाता है।
- **Arc picker** सिर्फ़ IV home पर काम करता है। दूसरे apps में वो edge Android के Back gesture के पास रहता है।
- **Lock screen:** Pixel का अपना छोटा clock भी दिखेगा। Settings → Display → Lock screen में *Double-line clock* off करें। Lock screen के widgets सिर्फ़ दिखते हैं, tap नहीं होते।
- **Call screen:** ये Pixel Phone app की screen के ऊपर दिखती है। Call के दौरान mute, speaker और keypad Pixel की screen पर मिलते हैं ("Phone screen" button)।
- Recents screen और notification shade नहीं बदले जा सकते।
