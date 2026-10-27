---
layout: default
title: WonderTales Privacy Policy
---

# WonderTales Privacy Policy

**Last updated: October 26, 2026**

**App:** WonderTales for Android (`com.wondertales.storybook`)

**App operator:** Jens Windau  
**Privacy contact:** wondertales.privacy@gmail.com  
**Operator location:** Menlo Park, California, United States

This policy describes WonderTales for an invitation-only Google Play internal test intended for parents and authorized adult caregivers participating in the United States. It is not a statement of worldwide availability or worldwide legal compliance. Please do not join this test from outside the United States. The app does not enforce a geographic restriction, and this statement does not prevent access from elsewhere.

**Internal-test feature status:** New AI illustration generation and live rewarded advertisements are not available in this test. Existing books, local photo/profile features, text previews, narration and sharing may remain available. The app still includes Firebase, Google ML Kit, Google AdMob and Google's consent SDK; disabled ads and generation do not mean the app is offline or that no information is processed.

The sections below distinguish current processing from the AI and advertising workflows that would apply if those features are offered later. Enabling them would require a separate readiness review and an updated notice where appropriate.

## 1. Intended users and children's information

WonderTales is primarily designed for parents to create personalized fairy tales for children ages 3 to 8. Children may read or listen to completed stories with a parent. Parents are intended to control photo selection, story creation and sensitive settings. This is an intended use, not a verified parent-only access restriction: the current app does not separate these controls behind an adult gate.

This does not mean that the app processes only adults' information. Adults may provide children's names, photographs and likenesses, and those details may appear in personalized stories and illustrations. Adult testers should supervise access, use synthetic profiles where possible, and avoid adding unnecessary real children's information during testing.

Only add another person's information if you have the authority and permissions required to do so. For a child, this includes appropriate parental or legal-guardian authorization and any additional requirements that apply where you live. Avoid uploading unnecessary sensitive information or photographs of people who have not agreed to the intended use.

The current app does not verify a user's age or parental status. Advertising consent is not parental authorization to process a child's photograph. If you believe information about a child was provided without appropriate authority, contact us using the privacy contact above so we can investigate and consider the available deletion steps.

## 2. Information stored on your device

WonderTales stores the following in its private app storage:

- Names and relationship labels you enter for family profiles.
- Cropped family photographs and photo hashes used for caching and matching a story request.
- Character assignments, language preferences and reading progress.
- Saved story text, generated illustrations and book metadata.
- Generation request identifiers and recovery records used to avoid repeating requests.
- Local rewarded-ad attempt state, so an interrupted or unconfirmed reward is not silently treated as a new attempt.

You do not need to add family photographs to read bundled text previews. Saved books are designed to remain readable offline once their files have been downloaded successfully.

## 3. Photo selection and cropping

You choose an image through Android's image-selection interface. WonderTales reads that selected image and its orientation information, then uses Google ML Kit face detection on the device to locate a face. When an image contains multiple faces, the app currently selects the largest detected face.

The app saves a recompressed, square 128-by-128-pixel crop for the family profile. It does not copy the complete selected original into its family-photo folder. The original may remain in your gallery, photo service or other location from which you selected it.

Google states that ML Kit processes these image inputs and detection results on the device, but ML Kit can contact Google for updates and send performance and usage metrics. On-device face detection therefore does not mean that every included SDK operates without network communication or data collection. See [Google ML Kit privacy information](https://developers.google.com/ml-kit/terms).

## 4. Personalized illustration generation and OpenAI

**New AI illustration generation is unavailable in this internal test.** Selecting a profile photograph still invokes the local processing described above. Disabling generation does not erase previously created books or cloud records.

If AI generation is enabled in a later version or test, the implemented workflow prepares selected face crops by resizing and recompressing them, then sends 256-by-256-pixel JPEG references, assigned character roles, selected names, story selection and language to our Firebase backend.

In that workflow, the backend uses selected names to personalize prewritten story text. To create illustrations, it sends selected face references and authored illustration instructions to OpenAI's image-generation API. The current illustration prompt uses story roles and visual descriptions rather than inserting the assigned family names or the complete personalized story text. The generated illustrations may nevertheless contain recognizable family likenesses.

Adding a profile is separate from requesting AI illustration generation. Selecting a photo for a profile does not by itself submit that photo to OpenAI. In an enabled generation workflow, a request may have already transmitted information before an interruption or failure is displayed.

The implemented backend passes reference-photo bytes to the provider during the request; it does not intentionally save those reference-photo files in Firebase Storage or Firestore. This does not establish that OpenAI retains no information. Provider safety processing, retention and data-use controls are separate from our temporary-image cleanup. See [OpenAI API data controls](https://developers.openai.com/api/docs/guides/your-data). We do not promise zero provider retention or immediate erasure of all provider-held copies.

## 5. Firebase, cloud records and service logs

WonderTales uses Google Firebase and Google Cloud services for authentication, backend functions, Firestore records and temporary illustration storage. Firebase sign-in and a backend connectivity check can run at launch even while new generation is disabled. Existing job lookup, registration or delivery recovery may also contact the backend when those flows are used; disabling generation is not a promise that all cloud communication stops.

The app automatically signs in using Firebase anonymous authentication if no Firebase user is already signed in. This creates a service identifier without asking you for an email address or password. "Anonymous" here does not mean that all activity is unidentifiable: requests, jobs, quotas and rewards can be associated with that identifier, and service providers may process network and device information.

Existing cloud records, and records created through available registration or recovery flows, can include the items below. Some items originate from earlier enabled generation or advertising workflows; this list does not mean new AI images or live ad rewards are being created during this test:

- Story and language selection, request identities, job identifiers, timestamps and request status.
- Prepared and completed personalized story text, which can contain assigned family names.
- Generated illustrations in temporary cloud storage.
- Illustration diagnostics, error categories and provider request identifiers.
- Generation usage, estimated-cost and reservation records used to prevent abuse and duplicate requests.
- Reward tickets, reward-verification receipts and single-use entitlement state when rewarded advertising is available.

Backend logging records operational information such as generation stages, job/provider request identifiers and error categories. The implemented logging avoids intentionally printing reference-photo bytes, API keys and complete personalized story text. This is not a promise that infrastructure logs contain no personal or linkable information: IP addresses, identifiers and technical diagnostics may be recorded by service providers.

See [Firebase privacy and security information](https://firebase.google.com/support/privacy) and [Google's Privacy Policy](https://policies.google.com/privacy).

## 6. Advertising and consent choices

**Live rewarded ads are unavailable in this internal test.** The release build keeps its live-ad request gate off. The app nevertheless contains Google AdMob components and advertising identifiers/permissions. An SDK startup provider can run before the app's explicit initialization call; disabling our ad-request flow does not establish that every SDK startup operation or data collection is disabled.

When the app launches, Google's User Messaging Platform (UMP) can contact Google to update consent information and display any required privacy messages. The app checks UMP's current permission before its rewarded-ad initialization, loading and display. If consent information cannot establish permission, the app does not treat that uncertainty as consent. UMP may recognize a valid choice from a previous session. Depending on your choices and region, permission to request ads is not necessarily permission for personalized advertising.

Where UMP requires it, Settings provides **Ad privacy options** so you can revisit the choices. You can also review advertising privacy controls available in Android and your Google account. Some features may be unavailable when an ad cannot be shown or its reward cannot be verified.

If rewarded ads are offered later, the implemented workflow passes an opaque server-issued reward ticket to AdMob for server-side reward verification. It does not intentionally place family names, profile photographs, story text or character-casting lists into AdMob targeting or that custom-data field. The ticket can be linked to the relevant account and job by our backend; it is not a claim of anonymous processing.

Google states that the Mobile Ads SDK collects and shares information including IP addresses, ad/product interactions, diagnostics and device/account identifiers. The Android app currently declares the advertising-ID permission. SDK processing is not limited to information we explicitly put into an ad request. See [Google Mobile Ads data disclosures](https://developers.google.com/admob/android/privacy/play-data-disclosure) and [Google's Privacy Policy](https://policies.google.com/privacy).

Advertising choices do not control information needed for a separately requested AI generation, cloud recovery, narration or sharing operation.

## 7. Analytics and crash diagnostics

The reviewed app does not contain a dedicated Firebase Analytics or Firebase Crashlytics integration or custom analytics-event calls. This does not mean that no usage or diagnostic data is collected. AdMob, ML Kit, Firebase/Google Cloud and other platform services may process technical, performance, security and interaction information as described above and in their own disclosures.

## 8. Read-aloud narration

Narration uses Android's TextToSpeech service and the voice engine installed on your device. The app prefers suitable offline voices. If you choose the optional online-voice mode, personalized story text may be sent to that voice-engine provider for speech processing. That provider's privacy and retention practices apply. Installing or managing voices can also involve the device's system settings and providers.

## 9. Sharing illustrations

Sharing is initiated by you through a preview and Android's share sheet. The app creates a cover or collage locally using existing book illustrations; it does not request additional AI artwork for that export.

Exports use the story's catalog title and WonderTales branding. The export routine does not include original reference photographs, character-casting lists or family names as metadata. Personalized illustrations can still reveal a person's likeness. The app re-encodes the exported image rather than copying original photo metadata.

Once you send an image to another app or person, that recipient or service handles its copy under its own practices. Deleting the book in WonderTales does not retract shared copies.

## 10. Retention

Different kinds of data have different retention behavior:

| Data | Current retention behavior |
|---|---|
| Local profiles, cropped photos and books | Kept in app storage until removed through available controls, app data is cleared, or the app is uninstalled, subject to device/filesystem behavior. |
| Local progress and recovery records | Can remain separately from a deleted profile or book. |
| Temporary generated cloud illustrations | A scheduled daily cleanup is designed to attempt deletion of images older than 48 hours. Under successful daily operation this is generally around 48–72 hours, but it is **not a guaranteed deadline or permanent-erasure promise**. |
| Personalized text and cloud job records | The reviewed implementation does not automatically delete these on the image-cleanup schedule. |
| Reward, usage, accounting and replay-prevention records | No automatic expiry is implemented in the reviewed code. |
| Temporary sharing exports | The app attempts to clean up exports older than 24 hours when cleanup runs; this is not a continuously enforced deadline. |
| Provider logs, backups and other provider-held data | Governed by the relevant provider arrangements and settings; they are not erased simply because a local file or temporary cloud image is deleted. |

Failures, access restrictions, service configuration, soft deletion, versions, backups, exports or security requirements can affect when copies cease to exist. We do not promise that all copies disappear within 48–72 hours or that every provider uses zero retention.

## 11. Deleting data and requesting assistance

- **Delete a family profile:** removes its profile record and invokes deletion of its local crop. It does not delete the original photo from your gallery, existing books containing the person's name or likeness, or previously transmitted cloud/provider data.
- **Delete a saved book:** removes the local book entry and its local book folder. It does not automatically delete associated cloud jobs, personalized text, operational records or shared copies.
- **Clear app storage or uninstall:** normally removes the app's local data. The app disables Android's standard app-backup setting, but this is not a guarantee about every device, transfer method or external copy. These actions do not automatically erase Firebase authentication records or server/provider data.
- **Request help:** contact wondertales.privacy@gmail.com for questions or requests concerning your information or a child's information you are authorized to manage. The app currently has no complete in-app account/cloud-data deletion workflow. We may need limited information to locate records and verify the request and your authority. Do not send passwords, access tokens, API keys or children's photographs in an initial email.

Requests are considered under applicable law and the available technical/provider processes. Some limited records may need to remain for security, fraud/replay prevention or legal obligations. We cannot delete copies independently held by recipients of images you shared. We do not promise that contacting us automatically completes deletion or that every third-party copy can be immediately erased.

## 12. Privacy requests, processing locations and security

Parents and authorized caregivers may contact wondertales.privacy@gmail.com to ask about information concerning them or a child they are authorized to represent, request review or correction, request deletion, or ask us to stop further collection associated with their participation. We will explain the available process and any applicable legal rights after identifying the relevant records and verifying authority. This contact route does not itself implement automatic access, deletion or provider erasure. The technical deletion limitations in section 11 still apply.

Additional rights may depend on applicable United States federal or state law and its applicability to the operator and processing. This policy does not claim that every state privacy statute applies or that every statutory exemption has been established. Changing or withdrawing advertising choices does not by itself delete previously processed data.

The backend functions are configured for Google's `us-central1` region in the United States. Other providers and service components may process information in other locations. A function's region is not a guarantee that all data remains in one country. Information may be processed outside your country under the arrangements applicable to the service providers.

The app is designed to use private app storage, HTTPS service connections and owner-scoped backend access. These measures do not provide an absolute security guarantee or end-to-end encryption against a provider that must process a reference photo or story text. Please protect your device and be careful when choosing photographs or sharing illustrations.

## 13. Contact and changes

For privacy questions or requests, contact:

**Jens Windau**  
**wondertales.privacy@gmail.com**  
**Menlo Park, California, United States**


This initial policy is scoped to the intended United States internal test. It does not assert that EU/UK representative requirements have been satisfied or that an exception applies. A broader distribution plan would require a separate jurisdiction and representative review.

We may update this policy to reflect changes to the app or its data practices, including before offering AI generation or live ads. The date above identifies the latest version. Additional notices or renewed choices will be provided where required.

## 14. This privacy-policy website

This page is intended to be hosted on GitHub Pages. GitHub states that it logs visitors' IP addresses for security purposes when they visit a Pages site. Those website visits are separate from the app's story and photo processing. See [GitHub Pages data collection](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages#data-collection) and [GitHub's Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement). This policy source includes no custom analytics, advertising scripts or collection forms.
