---
name: voices
description: Full voice list for edge-tts — all 323 voices across 70+ locales with usage examples
---

# Voice Selection

## List all available voices

```bash
edge-tts --list-voices
```

## Recommended English voices

| Voice | Gender | Style |
|-------|--------|-------|
| `en-US-AriaNeural` | Female | News, confident, positive |
| `en-US-GuyNeural` | Male | News, passionate |
| `en-US-JennyNeural` | Female | Friendly, considerate |
| `en-US-EricNeural` | Male | Rational |
| `en-US-ChristopherNeural` | Male | Reliable, authoritative |
| `en-US-AndrewNeural` | Male | Warm, confident, authentic |
| `en-US-AvaNeural` | Female | Expressive, caring |
| `en-US-EmmaNeural` | Female | Cheerful, clear |
| `en-GB-SoniaNeural` | Female | British, professional |
| `en-GB-RyanNeural` | Male | British, professional |
| `en-AU-NatashaNeural` | Female | Australian |

## Speech tuning

```bash
# Slower, lower pitch — dramatic narration
edge-tts --voice en-US-GuyNeural --rate=-15% --pitch=-5Hz \
  --text "In a world..." --write-media out.mp3

# Faster, energetic
edge-tts --voice en-US-JennyNeural --rate=+20% \
  --text "Act now!" --write-media out.mp3
```

> For negative values use `=` syntax: `--rate=-20%` not `--rate -20%`

## Filter by language

```bash
edge-tts --list-voices | grep "^en-"   # English
edge-tts --list-voices | grep "^es-"   # Spanish
edge-tts --list-voices | grep "^fr-"   # French
edge-tts --list-voices | grep "^de-"   # German
edge-tts --list-voices | grep "^zh-"   # Chinese
edge-tts --list-voices | grep "^ja-"   # Japanese
edge-tts --list-voices | grep "^ar-"   # Arabic
edge-tts --list-voices | grep "^pt-"   # Portuguese
```

---

## Full Voice List (323 voices)

| Voice | Gender | Locale |
|-------|--------|--------|
| af-ZA-AdriNeural | Female | Afrikaans (South Africa) |
| af-ZA-WillemNeural | Male | Afrikaans (South Africa) |
| am-ET-AmehaNeural | Male | Amharic (Ethiopia) |
| am-ET-MekdesNeural | Female | Amharic (Ethiopia) |
| ar-AE-FatimaNeural | Female | Arabic (UAE) |
| ar-AE-HamdanNeural | Male | Arabic (UAE) |
| ar-BH-AliNeural | Male | Arabic (Bahrain) |
| ar-BH-LailaNeural | Female | Arabic (Bahrain) |
| ar-DZ-AminaNeural | Female | Arabic (Algeria) |
| ar-DZ-IsmaelNeural | Male | Arabic (Algeria) |
| ar-EG-SalmaNeural | Female | Arabic (Egypt) |
| ar-EG-ShakirNeural | Male | Arabic (Egypt) |
| ar-IQ-BasselNeural | Male | Arabic (Iraq) |
| ar-IQ-RanaNeural | Female | Arabic (Iraq) |
| ar-JO-SanaNeural | Female | Arabic (Jordan) |
| ar-JO-TaimNeural | Male | Arabic (Jordan) |
| ar-KW-FahedNeural | Male | Arabic (Kuwait) |
| ar-KW-NouraNeural | Female | Arabic (Kuwait) |
| ar-LB-LaylaNeural | Female | Arabic (Lebanon) |
| ar-LB-RamiNeural | Male | Arabic (Lebanon) |
| ar-LY-ImanNeural | Female | Arabic (Libya) |
| ar-LY-OmarNeural | Male | Arabic (Libya) |
| ar-MA-JamalNeural | Male | Arabic (Morocco) |
| ar-MA-MounaNeural | Female | Arabic (Morocco) |
| ar-OM-AbdullahNeural | Male | Arabic (Oman) |
| ar-OM-AyshaNeural | Female | Arabic (Oman) |
| ar-QA-AmalNeural | Female | Arabic (Qatar) |
| ar-QA-MoazNeural | Male | Arabic (Qatar) |
| ar-SA-HamedNeural | Male | Arabic (Saudi Arabia) |
| ar-SA-ZariyahNeural | Female | Arabic (Saudi Arabia) |
| ar-SY-AmanyNeural | Female | Arabic (Syria) |
| ar-SY-LaithNeural | Male | Arabic (Syria) |
| ar-TN-HediNeural | Male | Arabic (Tunisia) |
| ar-TN-ReemNeural | Female | Arabic (Tunisia) |
| ar-YE-MaryamNeural | Female | Arabic (Yemen) |
| ar-YE-SalehNeural | Male | Arabic (Yemen) |
| az-AZ-BabekNeural | Male | Azerbaijani |
| az-AZ-BanuNeural | Female | Azerbaijani |
| bg-BG-BorislavNeural | Male | Bulgarian |
| bg-BG-KalinaNeural | Female | Bulgarian |
| bn-BD-NabanitaNeural | Female | Bengali (Bangladesh) |
| bn-BD-PradeepNeural | Male | Bengali (Bangladesh) |
| bn-IN-BashkarNeural | Male | Bengali (India) |
| bn-IN-TanishaaNeural | Female | Bengali (India) |
| bs-BA-GoranNeural | Male | Bosnian |
| bs-BA-VesnaNeural | Female | Bosnian |
| ca-ES-EnricNeural | Male | Catalan |
| ca-ES-JoanaNeural | Female | Catalan |
| cs-CZ-AntoninNeural | Male | Czech |
| cs-CZ-VlastaNeural | Female | Czech |
| cy-GB-AledNeural | Male | Welsh |
| cy-GB-NiaNeural | Female | Welsh |
| da-DK-ChristelNeural | Female | Danish |
| da-DK-JeppeNeural | Male | Danish |
| de-AT-IngridNeural | Female | German (Austria) |
| de-AT-JonasNeural | Male | German (Austria) |
| de-CH-JanNeural | Male | German (Switzerland) |
| de-CH-LeniNeural | Female | German (Switzerland) |
| de-DE-AmalaNeural | Female | German (Germany) |
| de-DE-ConradNeural | Male | German (Germany) |
| de-DE-FlorianMultilingualNeural | Male | German (Germany) — Multilingual |
| de-DE-KatjaNeural | Female | German (Germany) |
| de-DE-KillianNeural | Male | German (Germany) |
| de-DE-SeraphinaMultilingualNeural | Female | German (Germany) — Multilingual |
| el-GR-AthinaNeural | Female | Greek |
| el-GR-NestorasNeural | Male | Greek |
| en-AU-NatashaNeural | Female | English (Australia) |
| en-AU-WilliamMultilingualNeural | Male | English (Australia) — Multilingual |
| en-CA-ClaraNeural | Female | English (Canada) |
| en-CA-LiamNeural | Male | English (Canada) |
| en-GB-LibbyNeural | Female | English (UK) |
| en-GB-MaisieNeural | Female | English (UK) |
| en-GB-RyanNeural | Male | English (UK) |
| en-GB-SoniaNeural | Female | English (UK) |
| en-GB-ThomasNeural | Male | English (UK) |
| en-HK-SamNeural | Male | English (Hong Kong) |
| en-HK-YanNeural | Female | English (Hong Kong) |
| en-IE-ConnorNeural | Male | English (Ireland) |
| en-IE-EmilyNeural | Female | English (Ireland) |
| en-IN-NeerjaExpressiveNeural | Female | English (India) — Expressive |
| en-IN-NeerjaNeural | Female | English (India) |
| en-IN-PrabhatNeural | Male | English (India) |
| en-KE-AsiliaNeural | Female | English (Kenya) |
| en-KE-ChilembaNeural | Male | English (Kenya) |
| en-NG-AbeoNeural | Male | English (Nigeria) |
| en-NG-EzinneNeural | Female | English (Nigeria) |
| en-NZ-MitchellNeural | Male | English (New Zealand) |
| en-NZ-MollyNeural | Female | English (New Zealand) |
| en-PH-JamesNeural | Male | English (Philippines) |
| en-PH-RosaNeural | Female | English (Philippines) |
| en-SG-LunaNeural | Female | English (Singapore) |
| en-SG-WayneNeural | Male | English (Singapore) |
| en-TZ-ElimuNeural | Male | English (Tanzania) |
| en-TZ-ImaniNeural | Female | English (Tanzania) |
| en-US-AnaNeural | Female | English (US) — Cute, Cartoon |
| en-US-AndrewMultilingualNeural | Male | English (US) — Warm, Multilingual |
| en-US-AndrewNeural | Male | English (US) — Warm, Confident |
| en-US-AriaNeural | Female | English (US) — Positive, Confident |
| en-US-AvaMultilingualNeural | Female | English (US) — Expressive, Multilingual |
| en-US-AvaNeural | Female | English (US) — Expressive, Caring |
| en-US-BrianMultilingualNeural | Male | English (US) — Casual, Multilingual |
| en-US-BrianNeural | Male | English (US) — Approachable, Casual |
| en-US-ChristopherNeural | Male | English (US) — Reliable, Authority |
| en-US-EmmaMultilingualNeural | Female | English (US) — Cheerful, Multilingual |
| en-US-EmmaNeural | Female | English (US) — Cheerful, Clear |
| en-US-EricNeural | Male | English (US) — Rational |
| en-US-GuyNeural | Male | English (US) — Passionate |
| en-US-JennyNeural | Female | English (US) — Friendly, Considerate |
| en-US-MichelleNeural | Female | English (US) — Friendly, Pleasant |
| en-US-RogerNeural | Male | English (US) — Lively |
| en-US-SteffanNeural | Male | English (US) — Rational |
| en-ZA-LeahNeural | Female | English (South Africa) |
| en-ZA-LukeNeural | Male | English (South Africa) |
| es-AR-ElenaNeural | Female | Spanish (Argentina) |
| es-AR-TomasNeural | Male | Spanish (Argentina) |
| es-BO-MarceloNeural | Male | Spanish (Bolivia) |
| es-BO-SofiaNeural | Female | Spanish (Bolivia) |
| es-CL-CatalinaNeural | Female | Spanish (Chile) |
| es-CL-LorenzoNeural | Male | Spanish (Chile) |
| es-CO-GonzaloNeural | Male | Spanish (Colombia) |
| es-CO-SalomeNeural | Female | Spanish (Colombia) |
| es-CR-JuanNeural | Male | Spanish (Costa Rica) |
| es-CR-MariaNeural | Female | Spanish (Costa Rica) |
| es-CU-BelkysNeural | Female | Spanish (Cuba) |
| es-CU-ManuelNeural | Male | Spanish (Cuba) |
| es-DO-EmilioNeural | Male | Spanish (Dominican Republic) |
| es-DO-RamonaNeural | Female | Spanish (Dominican Republic) |
| es-EC-AndreaNeural | Female | Spanish (Ecuador) |
| es-EC-LuisNeural | Male | Spanish (Ecuador) |
| es-ES-AlvaroNeural | Male | Spanish (Spain) |
| es-ES-ElviraNeural | Female | Spanish (Spain) |
| es-ES-XimenaNeural | Female | Spanish (Spain) |
| es-GQ-JavierNeural | Male | Spanish (Equatorial Guinea) |
| es-GQ-TeresaNeural | Female | Spanish (Equatorial Guinea) |
| es-GT-AndresNeural | Male | Spanish (Guatemala) |
| es-GT-MartaNeural | Female | Spanish (Guatemala) |
| es-HN-CarlosNeural | Male | Spanish (Honduras) |
| es-HN-KarlaNeural | Female | Spanish (Honduras) |
| es-MX-DaliaNeural | Female | Spanish (Mexico) |
| es-MX-JorgeNeural | Male | Spanish (Mexico) |
| es-NI-FedericoNeural | Male | Spanish (Nicaragua) |
| es-NI-YolandaNeural | Female | Spanish (Nicaragua) |
| es-PA-MargaritaNeural | Female | Spanish (Panama) |
| es-PA-RobertoNeural | Male | Spanish (Panama) |
| es-PE-AlexNeural | Male | Spanish (Peru) |
| es-PE-CamilaNeural | Female | Spanish (Peru) |
| es-PR-KarinaNeural | Female | Spanish (Puerto Rico) |
| es-PR-VictorNeural | Male | Spanish (Puerto Rico) |
| es-PY-MarioNeural | Male | Spanish (Paraguay) |
| es-PY-TaniaNeural | Female | Spanish (Paraguay) |
| es-SV-LorenaNeural | Female | Spanish (El Salvador) |
| es-SV-RodrigoNeural | Male | Spanish (El Salvador) |
| es-US-AlonsoNeural | Male | Spanish (US) |
| es-US-PalomaNeural | Female | Spanish (US) |
| es-UY-MateoNeural | Male | Spanish (Uruguay) |
| es-UY-ValentinaNeural | Female | Spanish (Uruguay) |
| es-VE-PaolaNeural | Female | Spanish (Venezuela) |
| es-VE-SebastianNeural | Male | Spanish (Venezuela) |
| et-EE-AnuNeural | Female | Estonian |
| et-EE-KertNeural | Male | Estonian |
| fa-IR-DilaraNeural | Female | Persian (Iran) |
| fa-IR-FaridNeural | Male | Persian (Iran) |
| fi-FI-HarriNeural | Male | Finnish |
| fi-FI-NooraNeural | Female | Finnish |
| fil-PH-AngeloNeural | Male | Filipino |
| fil-PH-BlessicaNeural | Female | Filipino |
| fr-BE-CharlineNeural | Female | French (Belgium) |
| fr-BE-GerardNeural | Male | French (Belgium) |
| fr-CA-AntoineNeural | Male | French (Canada) |
| fr-CA-JeanNeural | Male | French (Canada) |
| fr-CA-SylvieNeural | Female | French (Canada) |
| fr-CA-ThierryNeural | Male | French (Canada) |
| fr-CH-ArianeNeural | Female | French (Switzerland) |
| fr-CH-FabriceNeural | Male | French (Switzerland) |
| fr-FR-BrigitteNeural | Female | French (France) |
| fr-FR-CelesteNeural | Female | French (France) |
| fr-FR-ClaudeNeural | Male | French (France) |
| fr-FR-CoralieNeural | Female | French (France) |
| fr-FR-DeniseNeural | Female | French (France) |
| fr-FR-EloiseNeural | Female | French (France) |
| fr-FR-HenriNeural | Male | French (France) |
| fr-FR-JacquelineNeural | Female | French (France) |
| fr-FR-JeromeNeural | Male | French (France) |
| fr-FR-JosephineNeural | Female | French (France) |
| fr-FR-MauriceNeural | Male | French (France) |
| fr-FR-RemyMultilingualNeural | Male | French (France) — Multilingual |
| fr-FR-VivienneMultilingualNeural | Female | French (France) — Multilingual |
| fr-FR-YvesNeural | Male | French (France) |
| fr-FR-YvetteNeural | Female | French (France) |
| ga-IE-ColmNeural | Male | Irish |
| ga-IE-OrlaNeural | Female | Irish |
| gl-ES-RoiNeural | Male | Galician |
| gl-ES-SabelaNeural | Female | Galician |
| gu-IN-DhwaniNeural | Female | Gujarati |
| gu-IN-NiranjanNeural | Male | Gujarati |
| he-IL-AvriNeural | Male | Hebrew |
| he-IL-HilaNeural | Female | Hebrew |
| hi-IN-MadhurNeural | Male | Hindi |
| hi-IN-SwaraNeural | Female | Hindi |
| hr-HR-GabrijelaNeural | Female | Croatian |
| hr-HR-SreckoNeural | Male | Croatian |
| hu-HU-NoemiNeural | Female | Hungarian |
| hu-HU-TamasNeural | Male | Hungarian |
| id-ID-ArdiNeural | Male | Indonesian |
| id-ID-GadisNeural | Female | Indonesian |
| is-IS-GudrunNeural | Female | Icelandic |
| is-IS-GunnarNeural | Male | Icelandic |
| it-IT-BenignoNeural | Male | Italian |
| it-IT-CalimeroNeural | Male | Italian |
| it-IT-CataldoNeural | Male | Italian |
| it-IT-DiegoNeural | Male | Italian |
| it-IT-ElsaNeural | Female | Italian |
| it-IT-FabiolaNeural | Female | Italian |
| it-IT-FiammaNeural | Female | Italian |
| it-IT-GianniNeural | Male | Italian |
| it-IT-GiuseppeMultilingualNeural | Male | Italian — Multilingual |
| it-IT-ImeldaNeural | Female | Italian |
| it-IT-IrmaNeural | Female | Italian |
| it-IT-IsabellaNeural | Female | Italian |
| it-IT-LisandroNeural | Male | Italian |
| it-IT-PalmiraNeural | Female | Italian |
| it-IT-PierinaNeural | Female | Italian |
| it-IT-RinaldoNeural | Male | Italian |
| ja-JP-AoiNeural | Female | Japanese |
| ja-JP-DaichiNeural | Male | Japanese |
| ja-JP-KeitaNeural | Male | Japanese |
| ja-JP-MayuNeural | Female | Japanese |
| ja-JP-NanamiNeural | Female | Japanese |
| ja-JP-NaokiNeural | Male | Japanese |
| ja-JP-ShioriNeural | Female | Japanese |
| jv-ID-DimasNeural | Male | Javanese |
| jv-ID-SitiNeural | Female | Javanese |
| ka-GE-EkaNeural | Female | Georgian |
| ka-GE-GiorgiNeural | Male | Georgian |
| kk-KZ-AigulNeural | Female | Kazakh |
| kk-KZ-DauletNeural | Male | Kazakh |
| km-KH-PisethNeural | Male | Khmer |
| km-KH-SreymomNeural | Female | Khmer |
| kn-IN-GaganNeural | Male | Kannada |
| kn-IN-SapnaNeural | Female | Kannada |
| ko-KR-BongJinNeural | Male | Korean |
| ko-KR-GookMinNeural | Male | Korean |
| ko-KR-HyunsuMultilingualNeural | Male | Korean — Multilingual |
| ko-KR-InJoonNeural | Male | Korean |
| ko-KR-JiMinNeural | Female | Korean |
| ko-KR-SeoHyeonNeural | Female | Korean |
| ko-KR-SoonBokNeural | Female | Korean |
| ko-KR-SunHiNeural | Female | Korean |
| ko-KR-YuJinNeural | Female | Korean |
| lo-LA-ChanthavongNeural | Male | Lao |
| lo-LA-KeomanyNeural | Female | Lao |
| lt-LT-LeonasNeural | Male | Lithuanian |
| lt-LT-OnaNeural | Female | Lithuanian |
| lv-LV-EveritaNeural | Female | Latvian |
| lv-LV-NilsNeural | Male | Latvian |
| mk-MK-AleksandarNeural | Male | Macedonian |
| mk-MK-MarijaNeural | Female | Macedonian |
| ml-IN-MidhunNeural | Male | Malayalam |
| ml-IN-SobhanaNeural | Female | Malayalam |
| mn-MN-BataaNeural | Male | Mongolian |
| mn-MN-YesuiNeural | Female | Mongolian |
| mr-IN-AarohiNeural | Female | Marathi |
| mr-IN-ManoharNeural | Male | Marathi |
| ms-MY-OsmanNeural | Male | Malay |
| ms-MY-YasminNeural | Female | Malay |
| mt-MT-GraceNeural | Female | Maltese |
| mt-MT-JosephNeural | Male | Maltese |
| my-MM-NilarNeural | Female | Burmese |
| my-MM-ThihaNeural | Male | Burmese |
| nb-NO-FinnNeural | Male | Norwegian |
| nb-NO-PernilleNeural | Female | Norwegian |
| ne-NP-HemkalaNeural | Female | Nepali |
| ne-NP-SagarNeural | Male | Nepali |
| nl-BE-ArnaudNeural | Male | Dutch (Belgium) |
| nl-BE-DenaNeural | Female | Dutch (Belgium) |
| nl-NL-ColetteNeural | Female | Dutch (Netherlands) |
| nl-NL-FennaNeural | Female | Dutch (Netherlands) |
| nl-NL-MaartenNeural | Male | Dutch (Netherlands) |
| pl-PL-AgnieszkaNeural | Female | Polish |
| pl-PL-MarekNeural | Male | Polish |
| ps-AF-GulNawazNeural | Male | Pashto |
| ps-AF-LatifaNeural | Female | Pashto |
| pt-BR-AntonioNeural | Male | Portuguese (Brazil) |
| pt-BR-FranciscaNeural | Female | Portuguese (Brazil) |
| pt-BR-ThalitaMultilingualNeural | Female | Portuguese (Brazil) — Multilingual |
| pt-PT-DuarteNeural | Male | Portuguese (Portugal) |
| pt-PT-RaquelNeural | Female | Portuguese (Portugal) |
| ro-RO-AlinaNeural | Female | Romanian |
| ro-RO-EmilNeural | Male | Romanian |
| ru-RU-DmitryNeural | Male | Russian |
| ru-RU-SvetlanaNeural | Female | Russian |
| si-LK-SameeraNeural | Male | Sinhala |
| si-LK-ThiliniNeural | Female | Sinhala |
| sk-SK-LukasNeural | Male | Slovak |
| sk-SK-ViktoriaNeural | Female | Slovak |
| sl-SI-PetraNeural | Female | Slovenian |
| sl-SI-RokNeural | Male | Slovenian |
| so-SO-MuuseNeural | Male | Somali |
| so-SO-UbaxNeural | Female | Somali |
| sq-AL-AnilaNeural | Female | Albanian |
| sq-AL-IlirNeural | Male | Albanian |
| sr-RS-NicholasNeural | Male | Serbian |
| sr-RS-SophieNeural | Female | Serbian |
| su-ID-JajangNeural | Male | Sundanese |
| su-ID-TutiNeural | Female | Sundanese |
| sv-SE-HilleviNeural | Female | Swedish |
| sv-SE-MattiasNeural | Male | Swedish |
| sv-SE-SofieNeural | Female | Swedish |
| sw-KE-RafikiNeural | Male | Swahili (Kenya) |
| sw-KE-ZuriNeural | Female | Swahili (Kenya) |
| sw-TZ-DaudiNeural | Male | Swahili (Tanzania) |
| sw-TZ-RehemaNeural | Female | Swahili (Tanzania) |
| ta-IN-PallaviNeural | Female | Tamil (India) |
| ta-IN-ValluvarNeural | Male | Tamil (India) |
| ta-LK-KumarNeural | Male | Tamil (Sri Lanka) |
| ta-LK-SaranyaNeural | Female | Tamil (Sri Lanka) |
| ta-MY-KaniNeural | Female | Tamil (Malaysia) |
| ta-MY-SuryaNeural | Male | Tamil (Malaysia) |
| ta-SG-AnbuNeural | Male | Tamil (Singapore) |
| ta-SG-VenbaNeural | Female | Tamil (Singapore) |
| te-IN-MohanNeural | Male | Telugu |
| te-IN-ShrutiNeural | Female | Telugu |
| th-TH-NiwatNeural | Male | Thai |
| th-TH-PremwadeeNeural | Female | Thai |
| tr-TR-AhmetNeural | Male | Turkish |
| tr-TR-EmelNeural | Female | Turkish |
| uk-UA-OstapNeural | Male | Ukrainian |
| uk-UA-PolinaNeural | Female | Ukrainian |
| ur-IN-GulNeural | Female | Urdu (India) |
| ur-IN-SalmanNeural | Male | Urdu (India) |
| ur-PK-AsadNeural | Male | Urdu (Pakistan) |
| ur-PK-UzmaNeural | Female | Urdu (Pakistan) |
| uz-UZ-MadinaNeural | Female | Uzbek |
| uz-UZ-SardorNeural | Male | Uzbek |
| vi-VN-HoaiMyNeural | Female | Vietnamese |
| vi-VN-NamMinhNeural | Male | Vietnamese |
| wuu-CN-XiaotongNeural | Female | Chinese (Wu) |
| wuu-CN-YunzheNeural | Male | Chinese (Wu) |
| yue-CN-XiaoMinNeural | Female | Chinese (Cantonese) |
| yue-CN-YunSongNeural | Male | Chinese (Cantonese) |
| zh-CN-XiaochenNeural | Female | Chinese (Mandarin) |
| zh-CN-XiaochenMultilingualNeural | Female | Chinese (Mandarin) — Multilingual |
| zh-CN-XiaohanNeural | Female | Chinese (Mandarin) |
| zh-CN-XiaomengNeural | Female | Chinese (Mandarin) |
| zh-CN-XiaomoNeural | Female | Chinese (Mandarin) |
| zh-CN-XiaoqiuNeural | Female | Chinese (Mandarin) |
| zh-CN-XiaorouNeural | Female | Chinese (Mandarin) |
| zh-CN-XiaoruiNeural | Female | Chinese (Mandarin) |
| zh-CN-XiaoshuangNeural | Female | Chinese (Mandarin) |
| zh-CN-XiaoxiaoNeural | Female | Chinese (Mandarin) |
| zh-CN-XiaoxiaoDialectsNeural | Female | Chinese (Mandarin) — Dialects |
| zh-CN-XiaoyiNeural | Female | Chinese (Mandarin) |
| zh-CN-XiaoyouNeural | Female | Chinese (Mandarin) |
| zh-CN-XiaoyuMultilingualNeural | Female | Chinese (Mandarin) — Multilingual |
| zh-CN-XiaozhenNeural | Female | Chinese (Mandarin) |
| zh-CN-YunfengNeural | Male | Chinese (Mandarin) |
| zh-CN-YunhaoNeural | Male | Chinese (Mandarin) |
| zh-CN-YunjianNeural | Male | Chinese (Mandarin) |
| zh-CN-YunxiNeural | Male | Chinese (Mandarin) |
| zh-CN-YunxiaNeural | Male | Chinese (Mandarin) |
| zh-CN-YunyangNeural | Male | Chinese (Mandarin) |
| zh-CN-YunyeNeural | Male | Chinese (Mandarin) |
| zh-CN-YunyiMultilingualNeural | Male | Chinese (Mandarin) — Multilingual |
| zh-CN-YunzeNeural | Male | Chinese (Mandarin) |
| zh-CN-YunfanMultilingualNeural | Male | Chinese (Mandarin) — Multilingual |
| zh-HK-HiuGaaiNeural | Female | Chinese (Cantonese, HK) |
| zh-HK-HiuMaanNeural | Female | Chinese (Cantonese, HK) |
| zh-HK-WanLungNeural | Male | Chinese (Cantonese, HK) |
| zh-TW-HsiaoChenNeural | Female | Chinese (Taiwanese Mandarin) |
| zh-TW-HsiaoYuNeural | Female | Chinese (Taiwanese Mandarin) |
| zh-TW-YunJheNeural | Male | Chinese (Taiwanese Mandarin) |
| zu-ZA-ThandoNeural | Female | Zulu |
| zu-ZA-ThembaNeural | Male | Zulu |
