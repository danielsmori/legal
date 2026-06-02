# Privacy Policy — Orlando Smart Concierge

**Last updated:** June 2, 2026
**Effective date:** Upon installation

This Privacy Policy explains how Orlando Smart Concierge ("we", "us", "the app"), published by Daniel Mori, collects, uses, and protects information about you when you use the iOS application Orlando Smart Concierge (the "App").

We deliberately keep data collection minimal. The summary below is the whole story; the rest of the document describes each item in more detail.

## Summary

| Data | Why we collect it | Where it goes | How long we keep it |
|---|---|---|---|
| Your approximate location (while the app is open) | Auto-detect which theme park you are in, warn you near flagged parking zones | Your device + our backend (Supabase, US-East region) for the duration of the request only | Not stored |
| Anonymous device key (App Attest) | Verify that requests come from a legitimate copy of the app | Our backend (Supabase) | Until you uninstall the app |
| Photos and camera frames you pick (Tax & Price Hunter, Lightning Lane Assistant) | Local OCR on your device | Stays on your device. We never upload images. | Not stored |
| OCR text from Lightning Lane screenshots | Translated and explained by an AI model | Sent to Google Gemini for inference. Not stored by us. Subject to [Google's terms](https://ai.google.dev/terms). | Not stored by us |
| Chat messages you send to Park Butler | Generate a reply | Sent to Google Gemini for inference. Not stored by us. | Not stored by us |
| Trip Pass purchase events | Unlock the paid features | Apple (App Store) + RevenueCat. We never see your payment details. | As long as Apple/RevenueCat retain receipts |
| IP address | Per-IP rate limiting only | Our backend (Supabase) | Rolling window, ≤ 24 hours |

We do **not** collect, store, or sell:
- Your name, email, phone number, or address
- Precise location data in the background
- Browsing history
- Contacts, calendars, microphone recordings, or health data
- Any advertising identifiers (IDFA)

---

## 1. Information We Collect

### 1.1 Location data

The App requests "When In Use" location authorization. Location is used in two ways:

- **Park detection.** When Park Butler or SafeStop is open, your approximate location is used on-device to figure out which Orlando-area park (Magic Kingdom, EPCOT, etc.) you are closest to. The park identifier — not your coordinates — is then attached to Park Butler requests so the assistant can give you park-specific answers.
- **SafeStop proximity.** When the SafeStop tab is open, your location is sent to our backend with a radius parameter to fetch a list of nearby safety zones. Your coordinates are used to compute the response and immediately discarded — they are not stored in any database.

The App never requests "Always" location authorization and never tracks you in the background. The parking-tracker feature stores the location of your car only when you explicitly tap "I parked here", and stores it only on your device.

### 1.2 App Attest device key

The first time the App talks to our backend on a real device, it generates a cryptographic key in the Secure Enclave (using Apple's App Attest framework) and sends the public part to our backend. We store the public key and a randomly generated client identifier. We use this to verify that subsequent requests come from a real, unmodified copy of the App. We do **not** receive your Apple ID, name, or any device identifier you could be re-identified by.

### 1.3 Photos and camera

The App uses your camera (for Tax & Price Hunter) and photo library (for Lightning Lane Assistant) only when you explicitly initiate one of those features. Optical Character Recognition (OCR) is performed entirely on your device using Apple's Vision framework. **Images themselves are never uploaded to our backend or to any third party.**

For Lightning Lane Assistant, the extracted text (not the image) is sent to Google Gemini for translation and explanation.

### 1.4 Chat messages

When you send a message to Park Butler, the message text plus a small amount of context (your detected park, the current language hint) is sent to Google's Gemini API. The response is streamed back to you. We do not store your chat history on our backend. Google may retain the request as described in [Google's Gemini API terms](https://ai.google.dev/terms).

### 1.5 Purchase information

Trip Pass purchases are processed by Apple's StoreKit and tracked by RevenueCat. We see the entitlement state (active / inactive / expired) and an opaque RevenueCat user identifier. **We never see your credit card information, your Apple ID, or your billing address.** Refund or billing questions are handled by Apple directly.

### 1.6 IP address

When your App makes a request to our backend, your IP address is briefly used for rate-limiting purposes (preventing abuse of free APIs). It is hashed into a rolling 24-hour bucket and never associated with any other piece of data about you.

---

## 2. How We Use the Information

We use the information described above to:

- Provide the features you explicitly use (park assistant, price calculator, safety map, Lightning Lane analyzer)
- Verify that requests come from the genuine App and not from automated abuse
- Enforce reasonable rate limits on third-party AI and currency APIs
- Process and validate your Trip Pass purchase
- Diagnose and fix bugs

We do **not**:

- Use your data for advertising
- Sell, rent, or share your data with third-party advertisers or data brokers
- Build advertising or behavioral profiles
- Train any AI model on your data (Google's data-use policy applies to messages sent through their API; see [Google's terms](https://ai.google.dev/terms))

---

## 3. Sharing of Information

We share information only with the following service providers, each used strictly to operate the App:

| Provider | Purpose | Data shared |
|---|---|---|
| Supabase (database + edge functions) | Backend hosting | Anonymous device key, IP for rate limiting, exchange-rate and wait-time queries |
| Google Gemini | AI replies for Park Butler and Lightning Lane | Your message text + context (park identifier, language hint) + OCR text from Lightning Lane |
| ExchangeRate-API | USD↔BRL and other currency rates | None of your data — we only query their public exchange rate endpoint |
| themeparks.wiki | Theme park wait times | None of your data — we poll their public API on a schedule, independent of you |
| Apple App Store / StoreKit | Trip Pass purchase | Your Apple ID handles the transaction; we receive only an opaque transaction identifier |
| RevenueCat | Trip Pass entitlement tracking | Opaque user identifier, purchase events |

We disclose information when required by law (subpoena, court order, etc.), but the structure of the App is designed so that the data we have about you is intentionally minimal.

---

## 4. Children's Privacy

The App is not directed at children under 13. We do not knowingly collect personal information from children under 13. If you believe a child has provided us with personal information, please contact us at [support@orlandosmartconcierge.app](mailto:support@orlandosmartconcierge.app).

---

## 5. Your Rights

You can:

- **Delete your data.** Uninstall the App. All on-device data (parking tracker, App Attest key) is removed automatically. Email us at [support@orlandosmartconcierge.app](mailto:support@orlandosmartconcierge.app) if you also want us to remove your anonymous device-key record from our backend.
- **Manage your purchase.** Cancel or request refunds for Trip Pass through your Apple ID (Settings → Apple ID → Subscriptions or [reportaproblem.apple.com](https://reportaproblem.apple.com)).
- **Revoke permissions.** Location, camera, photos, notifications: iOS Settings → Apps → Orlando Smart Concierge.

If you are in the European Union, the United Kingdom, Brazil (LGPD), or California (CCPA/CPRA), you have additional rights to access, correct, and delete personal data. Because we collect so little personally identifiable information in the first place, requests under these laws typically amount to "delete my anonymous device record" — which we will do on request.

---

## 6. Data Retention

| Data | Retention |
|---|---|
| Location | Not stored. Used in transit only. |
| Anonymous device key | Stored until you ask us to delete it or you uninstall the App |
| OCR images | Not stored. Stay on your device. |
| Chat / OCR text sent to Google Gemini | We do not store it. Subject to Google's retention policy. |
| Trip Pass purchase metadata | As long as Apple and RevenueCat retain receipts (typically the life of your Apple ID) |
| IP for rate limiting | ≤ 24 hours |

---

## 7. Security

- All requests between the App and our backend use HTTPS / TLS 1.3.
- Backend rows that touch any user state (`attested_clients`, etc.) are protected by Row-Level Security and only accessible by the backend service role.
- App Attest signatures cryptographically verify that requests come from a legitimate App copy.
- We never receive your payment card details — Apple handles the transaction.

No system is perfectly secure. If you discover a security issue, please email [support@orlandosmartconcierge.app](mailto:support@orlandosmartconcierge.app).

---

## 8. International Transfers

The App is operated from the United States. Backend infrastructure is hosted in the US-East region of Supabase. If you use the App from outside the United States, your data will be transferred to and processed in the United States.

---

## 9. Changes to This Policy

We may update this Privacy Policy from time to time. Material changes will be reflected by updating the "Last updated" date at the top. Continued use of the App after a change indicates acceptance of the updated policy.

The full history of changes is publicly viewable in the [Git history of this document](https://github.com/danielsmori/legal/commits/main/orlando-smart-concierge/privacy-policy.md).

---

## 10. Contact

Questions, complaints, or data-deletion requests:

**Daniel Mori**
Email: [support@orlandosmartconcierge.app](mailto:support@orlandosmartconcierge.app)
