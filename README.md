# Mandarin Live Translator — prototype

## Included
- Browser speech recognition set to Mandarin (zh-CN), when supported by iOS Safari.
- Pinyin via pinyin-pro CDN.
- Translation to Indonesian and/or English via MyMemory public translation endpoint.
- Notes saved in localStorage on this device, TXT export.
- Small built-in medical glossary.
- Basic extractive session summary (not AI-generated).

## Important limitations
1. This is an untested prototype until you run it on your own iPhone.
2. SpeechRecognition support varies by iOS/Safari version. If `SpeechRecognition`/`webkitSpeechRecognition` is missing or unstable, live transcription needs a server-side speech-to-text provider.
3. MyMemory is a public service with quotas/availability limits. Do not send confidential patient information. Medical translations must be checked.
4. Live recognition may stop when Safari is backgrounded or the screen locks. Keep the page open and screen awake.
5. Notes remain in localStorage in this browser. Clearing Safari website data can remove them.
6. The service worker/PWA cache works only when hosted over HTTPS (or localhost).
7. Ask the lecturer/institution before recording a class.

## Deploy to GitHub Pages using iPhone
1. In Safari, open GitHub and sign in.
2. Create a new public repository named `mandarin-live-translator`.
3. Upload `index.html`, `manifest.webmanifest`, and `sw.js` from this ZIP. GitHub's website may be easier in desktop mode; if the upload workflow is awkward on iPhone, use a computer later.
4. In repository Settings → Pages, choose deploy from the `main` branch and root folder.
5. Wait for GitHub Pages to publish, then open the HTTPS URL it gives you.
6. Test the "Uji terjemahan dengan teks" section first. Then tap "Mulai live" and allow microphone access.
7. To add to Home Screen: Safari Share → Add to Home Screen. If offered, enable Open as Web App.

## Test checklist
- [ ] HTTPS URL loads.
- [ ] Manual Mandarin text produces translation in both languages.
- [ ] Pinyin appears.
- [ ] Microphone permission prompt appears.
- [ ] Spoken Mandarin creates transcript.
- [ ] Translation updates after a phrase.
- [ ] Notes save after refresh.
- [ ] TXT export downloads/opens.
- [ ] Test again with screen awake and Safari in foreground.

## Next production step
For robust continuous speech-to-text and reliable translation, add a server endpoint and a speech-to-text provider. Keep provider API keys on the server; never paste secret keys into `index.html` or a public GitHub repository.
