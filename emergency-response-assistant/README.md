# Saathi — Emergency Response Assistant

A browser-based, mobile-friendly MVP for emergency symptom screening in India. It uses a fixed, reviewable rule set for urgency; it does not use an AI model or provide a diagnosis.

## Run locally

Serve this folder from `localhost` so browser geolocation, voice features, and Web Crypto can work:

```powershell
python -m http.server 8000
```

Then open [http://localhost:8000](http://localhost:8000). The service worker caches the app shell for later offline access. Install it from a supporting browser’s install control if desired.

## Included

- English and Hindi interface, with responsive layout, keyboard focus styles, high-contrast toggle, and optional speech input/output when supported by the browser.
- Sequential symptom assessment and deterministic RED / ORANGE / YELLOW / GREEN escalation rules.
- Explicit user-initiated `tel:112` links and first-aid references for five scenarios.
- Optional browser geolocation, editable location text, and a consent-gated SMS draft. The user reviews and sends the message themselves.
- Optional medical card encrypted in browser storage using PBKDF2-derived AES-GCM. The passphrase is never saved.
- Session-only incident history and an offline-cached static app shell.

## Privacy and deployment limits

There is no backend, account system, analytics, notification service, or automatic alerting. Screening details and recent checks remain in page memory and disappear when the tab closes. A medical card is stored only as ciphertext in this browser; a lost passphrase cannot be recovered. Location is requested only after the user taps the location button. Sharing opens a prefilled SMS app after consent and requires the user to send it.

This MVP has not had clinical, legal, native-device, or security review. First-aid content and escalation rules need review by qualified emergency-care professionals before real-world deployment. Browser/PWA `tel:` behavior, speech support, and geolocation permissions vary by device. The app is not a substitute for calling 112 or seeking professional medical care.
