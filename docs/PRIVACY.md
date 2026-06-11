# Finovo Privacy Policy

**In effect from:** June 11, 2026

Finovo is an iPhone and iPad app published by **ZXApps** (operated by the developer Ghayor Abbas, reachable at the contact address listed in [§20](#20-how-to-reach-us)). It helps you track expenses and income, scan and organize receipts, manage wallets and budgets, follow recurring bills, and split costs with other people. This document explains, in plain language, what the app does with information on your device — and what it deliberately avoids doing.

In this document, "**Finovo**" or "the app" refers to the application; "**ZXApps**," "**we**," "**us**," or "**our**" refers to the publisher.

The short version is below in [§1](#1-the-shortest-possible-summary). The long version takes the same statements apart and explains them piece by piece.

---

## Index

1. 1[The shortest possible summary](#1-the-shortest-possible-summary)
2. 2[How Finovo is built](#2-how-finovo-is-built)
3. 3[Inventory of data the app reads and stores](#3-inventory-of-data-the-app-reads-and-stores)
4. 4[Things Finovo never does](#4-things-finovo-never-does)
5. 5[Every permission the app may ask for](#5-every-permission-the-app-may-ask-for)
6. 6[Where your data physically lives](#6-where-your-data-physically-lives)
7. 7[Network behavior of the app](#7-network-behavior-of-the-app)
8. 8[Advertising and Google AdMob](#8-advertising-and-google-admob)
9. 9[Subscriptions](#9-subscriptions)
10. 10[Notifications and reminders](#10-notifications-and-reminders)
11. 11[Apple frameworks the app relies on](#11-apple-frameworks-the-app-relies-on)
12. 12[Security posture](#12-security-posture)
13. 13[Use by minors](#13-use-by-minors)
14. 14[Controls you always have through iOS](#14-controls-you-always-have-through-ios)
15. 15[Notice for users in the EU, the EEA, the UK, and Switzerland](#15-notice-for-users-in-the-eu-the-eea-the-uk-and-switzerland)
16. 16[Notice for users in California](#16-notice-for-users-in-california)
17. 17[Notice for users elsewhere](#17-notice-for-users-elsewhere)
18. 18[Cross-border transfers](#18-cross-border-transfers)
19. 19[Updates to this document](#19-updates-to-this-document)
20. 20[How to reach us](#20-how-to-reach-us)

---

## 1. The shortest possible summary

If you stop reading after this section, take these facts with you:

1. 1The financial data you enter — expenses, income, receipts, wallets, budgets, splits — is **stored on your device**. ZXApps does not operate a server that stores it.
2. 2The app never uploads your receipts, transactions, or attachments to us. Receipt text recognition runs **on your device**.
3. 3**iCloud sync is optional and off by default.** If you turn it on, your data syncs only through **your own private iCloud account**; we never receive a copy.
4. 4We do **not** use any third-party analytics, attribution, or crash-reporting SDK.
5. 5The **free tier shows ads through Google AdMob**, which involves limited data processing by Google. **Subscribing removes ads.**
6. 6We do **not** sell your personal information for money.
7. 7You can use the app as a **Guest** with no account, or with **Sign in with Apple**. We never ask for a password.
8. 8Permissions (Camera, Photos, Location, Notifications) are optional and independent. Denying one only disables that one feature.
9. 9Deleting the app from your device deletes the local data the app stored on that device.

The remainder of this document expands on each of these claims so you can verify them.

---

## 2. How Finovo is built

Finovo is what the iOS community calls a **local-first** app. Practically, that means:

- All of your financial records are created, stored, and analyzed on the same device you use. The app does not maintain a backend service, user database, or login system of its own.
- Your data is held in an on-device database (Apple's **SwiftData**) and, only if you switch it on, mirrored to **your private iCloud** through Apple's CloudKit. There is no ZXApps-operated copy in the middle.
- Receipt scanning uses Apple's on-device document camera and the **Vision** framework for text recognition. Receipt images are read and parsed locally and are never sent to us or to any third party for processing.
- The one third-party component in the app is **Google AdMob**, used to show ads on the free tier. AdMob is described in detail in [§8](#8-advertising-and-google-admob). Apart from advertising, the app embeds no analytics, marketing, social-media, or external crash-reporting SDKs.

The reason these architectural choices matter for privacy is straightforward: the app keeps your financial life on your device, and the only data that leaves it does so through services you control (iCloud, the App Store) or through advertising you can remove by subscribing.

---

## 3. Inventory of data the app reads and stores

The sections below list, by category, the information Finovo touches while it runs. **Except for advertising data described in [§8](#8-advertising-and-google-admob), every item here is processed and stored only on your device** (and in your private iCloud if you enable sync).

### 3.1 Account information

If you choose **Sign in with Apple**, the app stores an Apple-provided user identifier and — only if you choose to share them on first sign-in — your name and email address (which may be Apple's private relay address). If you continue as a **Guest**, none of this is collected. This information stays on your device (and your private iCloud if sync is on). We never receive it on a server we control.

### 3.2 The financial records you enter

Finovo stores what you record, which may include: expenses and receipts, income, merchant and source names, amounts and currencies, dates, categories, notes, payment-method labels, wallets and account balances, budgets, recurring bills and subscriptions, and bill-split details — including names of people you add to a split.

### 3.3 Receipt images and documents

When you scan a receipt or attach an image or PDF, the file is stored with its record on your device (and your private iCloud if sync is on). Text recognition (OCR) runs **on your device** using Apple's Vision framework to suggest the amount, date, and merchant. **Receipt images are never uploaded to us or to any third party for processing.**

### 3.4 Your current location, on demand

If you choose to add a place to an expense, the app uses your device location **once, at that moment**, and turns it into a readable place name. Location is used only when you request it, never in the background, and only the resulting place text is stored with that record. The app does not build a location history or derive your home or work address.

### 3.5 App-internal state

Finovo keeps a small amount of bookkeeping on the device: whether onboarding/setup is complete, your selected currency, notification preferences, your iCloud-sync choice, and a cached copy of your subscription status reported by StoreKit. Your profile name/email (from Sign in with Apple) and currency may sync through your private iCloud so your devices stay consistent.

---

## 4. Things Finovo never does

For clarity, here are things the app does **not** do:

- It does not sell your personal information for money.
- It does not upload your receipts, transactions, balances, or attachments to a ZXApps server — there is no such server.
- It does not use a third-party **analytics** SDK, **attribution** SDK, or external **crash reporter**. (Firebase was removed from the app.)
- It does not use your financial data to target ads. Advertising data and your financial records are kept entirely separate.
- It does not read your messages, browsing history, health data, or data from other apps.
- It does not require you to create an account or share a password.
- It does not perform background location tracking.

The single exception to "nothing leaves the device" is the advertising on the free tier, which is explained honestly and in full in [§8](#8-advertising-and-google-admob).

---

## 5. Every permission the app may ask for

Finovo requests only the permissions below, and only at the moment a feature you tapped on requires them.


Saying "no" to any prompt simply disables the feature that needed it (and, for tracking, results in non-personalized ads). The rest of the app continues to work.

---

## 6. Where your data physically lives

Because everything except advertising data is on-device, it helps to know which location holds what:


Nothing in this table is uploaded to ZXApps. On-device storage relies on the same hardware-backed device encryption iOS provides whenever your device is locked.

---

## 7. Network behavior of the app

Finovo does not contact a ZXApps-owned server — there isn't one. Outbound network activity during use comes from these sources:

- **Google AdMob** requests ads from Google's ad servers on the free tier. This is described in [§8](#8-advertising-and-google-admob).
- **StoreKit** contacts Apple's App Store servers when you view subscription options, purchase, restore, or when your entitlement is refreshed. Operated by Apple, not by us.
- **iCloud / CloudKit** synchronizes your data with your private iCloud account, if you enable sync. Operated by Apple.
- **MapKit / Apple's reverse-geocoder** may turn a coordinate into a readable place name when you add a location to an expense. This call goes to Apple, not to us.

Apart from AdMob, the app makes **no** analytics requests, telemetry pings, attribution callbacks, or webhook calls to any third party, and sends none of your financial data anywhere.

---

## 8. Advertising and Google AdMob

The free tier of Finovo is supported by ads served through **Google AdMob** (operated by Google). This is the one part of the app where data is processed by a third party, so here is the full picture:

- **Content controls.** We configure AdMob to **exclude adult (18+), gambling, and sexually explicit ad content** to suit a personal-finance audience. We do not control, and cannot guarantee, the specific ads delivered.
- **Data Google may process.** To serve, cap, and measure ads and to detect fraud, Google and its ad-technology partners may process a device advertising identifier, IP address, coarse (IP-derived) location, device and operating-system information, and ad-interaction events. Google acts as an independent party for this processing under its own policies.
- **Your financial data is never used for ads.** Advertising runs separately from your records; the app does not share your transactions, receipts, or balances with advertisers.
- **Personalized vs. non-personalized ads and App Tracking Transparency.** If personalized advertising is enabled, iOS will show Apple's **App Tracking Transparency (ATT)** prompt asking your permission to track. If you **deny** (or if only non-personalized ads are used), you will see **non-personalized/contextual** ads, which use limited data for frequency capping and measurement but not for cross-app tracking. You can change this anytime in **Settings → Privacy & Security → Tracking** and **→ Apple Advertising**.
- **Google's policies.** Google's handling of this data is described at [https://policies.google.com/privacy](https://policies.google.com/privacy) and [https://policies.google.com/technologies/partner-sites](https://policies.google.com/technologies/partner-sites). AdMob specifics are at [https://support.google.com/admob/answer/6128543](https://support.google.com/admob/answer/6128543).
- **Removing ads.** Purchasing a subscription removes ads and the associated ad processing.

---

## 9. Subscriptions

Finovo is free to install and use on an ad-supported basis. Advanced features and an ad-free experience are unlocked through an optional auto-renewing subscription, sold by Apple via the App Store using Apple's **StoreKit** framework.

What this means in practice:

- Apple — not us — sees your payment method, billing address, and Apple ID.
- The only thing the app receives from StoreKit is a signed entitlement indicating whether your Apple ID currently has an active subscription. No payment identifiers travel with that signal.
- Price, billing period, and any free trial are shown on the purchase screen before you buy.
- Auto-renewal, cancellation, refunds, and Family Sharing are governed by Apple's standard subscription policies. You can manage or cancel a subscription at any time in **Settings → [Your Name] → Subscriptions** on your device.

Apple's processing of your purchase is described in Apple's privacy policy and the Apple Media Services Terms.

---

## 10. Notifications and reminders

If you turn them on, Finovo schedules **local notifications** (expense reminders and budget alerts) through iOS. These are produced by your device and never go through a push server. The app does not register for remote push notifications and never transmits a push device token. Adjust these anytime in **Settings → Notifications → Finovo**.

---

## 11. Apple frameworks the app relies on

For transparency, here are the Apple-provided system frameworks Finovo uses for user-facing features:

- **SwiftData** and **Foundation** — local storage and standard utilities.
- **CloudKit** — optional sync to your private iCloud.
- **AuthenticationServices** — Sign in with Apple.
- **VisionKit** — the on-device document camera for receipt scanning.
- **Vision** — on-device text recognition (OCR) of scanned receipts.
- **PhotosUI / PhotoKit** — picking an image to attach.
- **Core Location** — only when you add a location to an expense.
- **MapKit** — turning a coordinate into a readable place name.
- **StoreKit** — subscriptions.
- **UserNotifications** — scheduling local reminders.

The only third-party SDK in the app is **Google Mobile Ads (AdMob)**, covered in [§8](#8-advertising-and-google-admob).

---

## 12. Security posture

Because your financial data stays on the device (and your private iCloud), the security model is essentially the security model of iOS itself:

- **App sandbox.** iOS prevents other apps from reading Finovo's local container.
- **Hardware-backed encryption.** When your device is locked, on-device storage is encrypted using the device's hardware keys.
- **Private iCloud.** When sync is on, data is stored in your own iCloud private database, accessible only through your Apple account — not by us.
- **Least-privilege permissions.** Each permission is requested only when the matching feature is used.
- **No ZXApps server.** Because the app never sends your financial data to a server we operate, classes of risk like "server breach" of your records do not apply.

No technical system is ever provably perfect, but the smaller the surface area, the smaller the risk — and Finovo's is intentionally small.

---

## 13. Use by minors

Finovo is a general-audience finance utility and is not directed at children under **13**. We do not knowingly collect personal data from children under 13 (or under the higher digital age of consent where applicable, such as 16 in parts of the EU). Purchasing a subscription requires you to be 18 or older, or to have a parent's or guardian's consent. If you believe a minor has used Finovo in a way that raises a privacy concern, please write to the address in [§20](#20-how-to-reach-us).

---

## 14. Controls you always have through iOS

You don't need to file a written request to control what Finovo can see. iOS gives you the tools:

- **Settings → Privacy & Security → Camera / Photos / Location** — grant, narrow, or revoke each permission independently.
- **Settings → Privacy & Security → Tracking** and **→ Apple Advertising** — control ad tracking and personalization.
- **Settings → Notifications → Finovo** — mute reminders and alerts.
- **Settings → [Your Name] → Subscriptions** — cancel a subscription.
- **Settings → [Your Name] → iCloud** — remove Finovo's synced data from your iCloud.
- **Long-press the Finovo icon → Remove App → Delete App** — remove the app and its local data from the device.

These controls are immediate and honored by iOS itself.

---

## 15. Notice for users in the EU, the EEA, the UK, and Switzerland

This section provides additional information required by the EU General Data Protection Regulation (GDPR), the UK GDPR, and the Swiss FADP.

**Controller.** ZXApps, the publisher of Finovo, acts as the controller of the limited personal data processed in connection with the app. For advertising, **Google** also acts as a controller/processor of the data described in [§8](#8-advertising-and-google-admob) under its own policies.

**Legal bases.**

- **Article 6(1)(b)** — performance of a contract — when you ask the app to do something for you (record a transaction, scan a receipt, sync your data, process a subscription).
- **Article 6(1)(a)** — consent — for permissions you grant through iOS (Camera, Photos, Location, Notifications) and, where applicable, for personalized advertising via the ATT prompt. You can withdraw consent at any time.
- **Article 6(1)(f)** — legitimate interests — for keeping the app secure, remembering your preferences, and showing advertising that funds the free tier.

**Your rights.** Subject to GDPR conditions, you have the rights of access (Art. 15), rectification (Art. 16), erasure (Art. 17), restriction (Art. 18), portability (Art. 20), objection (Art. 21), not being subject to solely automated decision-making (Art. 22), which the app does not perform, and withdrawal of consent (Art. 7(3)).

Because Finovo keeps your records on your own device and iCloud, the fastest ways to exercise these rights are also the most direct: edit or delete records inside the app, revoke an iOS permission, turn off iCloud sync, or delete the app. For a written response about a specific GDPR right, write to the address in [§20](#20-how-to-reach-us) and we will respond within one month (extendable by two months for complex matters, with notice to you).

**Complaints.** You may lodge a complaint with your local supervisory authority:

- European Data Protection Board: [https://edpb.europa.eu/](https://edpb.europa.eu/)
- UK Information Commissioner's Office: [https://ico.org.uk/](https://ico.org.uk/)
- Swiss FDPIC: [https://www.edoeb.admin.ch/](https://www.edoeb.admin.ch/)

---

## 16. Notice for users in California

This section addresses disclosures expected under the California Consumer Privacy Act, as amended by the California Privacy Rights Act (the **CCPA**).

**Categories collected.** Finovo stores the financial records and account information you provide on your device. For advertising on the free tier, identifiers (such as a device advertising identifier and IP address) and internet/network activity may be processed by Google as described in [§8](#8-advertising-and-google-admob).

**"Sale" and "sharing."** We do **not** sell your personal information for money. However, the use of **personalized advertising** may be considered "sharing" of identifiers for "cross-context behavioral advertising" under the CCPA. **You can opt out** by declining the ATT prompt, using **Settings → Privacy & Security → Tracking / Apple Advertising**, or by subscribing to remove ads. We do not knowingly share the financial records you enter.

**Your CCPA rights.** You have the right to know, to delete, to correct, to opt out of sale/sharing, to limit the use of sensitive personal information, and to be free from retaliation for exercising these rights. To submit a request, email the address in [§20](#20-how-to-reach-us); we will respond within the timeframes California law sets. Authorized agents may submit a request with proof of authorization.

---

## 17. Notice for users elsewhere

If you live in a jurisdiction not specifically named above — for example, Brazil (LGPD), Canada (PIPEDA), Australia (Privacy Act 1988), Japan (APPI), South Korea (PIPA), or others — many of the rights described in [§15](#15-notice-for-users-in-the-eu-the-eea-the-uk-and-switzerland) and [§16](#16-notice-for-users-in-california) have analogues in your local law. Because Finovo keeps your data on your device, the iOS-level controls in [§14](#14-controls-you-always-have-through-ios) are usually the most direct way to enforce them. For a written response, write to the email in [§20](#20-how-to-reach-us).

---

## 18. Cross-border transfers

No international transfer of your financial records occurs through normal use of Finovo, because those records stay on your device and your private iCloud.

Advertising data processed by Google (see [§8](#8-advertising-and-google-admob)) may be processed in countries other than yours; Google applies safeguards (such as standard contractual clauses) as required by law. If you email us, the content of that email passes through and is retained by the email service we use to read and reply to it.

---

## 19. Updates to this document

If we change this Privacy Policy, the **"In effect from"** date at the top will move. For material changes — for example, adding a new third-party SDK, or any change that alters the on-device-first nature of the app — we will additionally display a notice inside the app the next time you open it. Continued use of Finovo after a revised date is taken as acceptance of the revised text, except where local law requires explicit consent.

---

## 20. How to reach us

For any question, request, or report related to this Privacy Policy:

- **Publisher:** ZXApps (Ghayor Abbas)
- **Email:** zxapps1993@gmail.com
- **Subject prefix that helps us route faster:** "Privacy — Finovo —"

We do our best to reply within the timeframes required by applicable law and to answer in plain language.

---

*If you ever find a behavior of Finovo that does not match a statement in this document, please tell us. We treat any such mismatch as a bug to fix, not a definition to broaden.*
