# GAUNTRY BETA PRIVACY POLICY

**Version:** 1.0  
**Effective Date:** Upon first distribution to an external beta tester  
**Application:** Gauntry (Android 12 or later)  
**Developer:** Steve Aiello, doing business as hacken4u  
**Contact:** hacken@hacken4u.com

## 1. Scope and overview

This Privacy Policy explains how the Gauntry beta application handles information on the Android device where it is installed, and what information may be disclosed through use of its network-testing features. Gauntry is a cybersecurity traffic interception and testing application. It is intended for testing systems for which you have sufficient authorization. Because it can capture complete HTTP and HTTPS communications, data in Gauntry may include sensitive information belonging to you or others. Do not capture data without authorization.

Gauntry currently has no Gauntry user account or login, advertising, in-app analytics, dedicated crash-reporting service, or cloud synchronization. It does not generate an advertising, account, device, or installation identifier. This statement concerns Gauntry's application features; system services, the embedded browser engine, destination websites, and network providers can still observe information as described below.

## 2. Information collected or processed by the app

**Captured network transactions.** When you enable capture or direct traffic through Gauntry, it may save the full URL, hostname, path, port, request method, headers, response status, timestamps, and request and response bodies. This includes, if present, cookies, authorization headers, API keys, passwords, session tokens, personal information, and other contents of the traffic. When VPN selection is used, it may save the source application's package name and Android application UID. Gauntry can retain both original and modified versions of intercepted communications.

**Testing and analysis records.** Gauntry stores or processes locally configured projects (including project name, client name, scope notes, and authorization date), request replay data, saved authorization-testing identities and their header values, testing requests, results, filters, and selected VPN target application names. These records may contain credentials or other sensitive information. Certain analysis views, such as the API map and inspection of JWTs, derive information from captured data in memory rather than creating a separate stored copy; sending data into other testing features can create new saved records.

**Configuration and acceptance.** A local settings file holds the proxy port and the accepted EULA version and acceptance timestamp. This settings file is not encrypted. The acceptance record does not include an account, tester, device, or installation identifier, and is not sent to Gauntry servers.

**Local device information.** To operate its capture, certificate, application-selection and time-integrity features, Gauntry may inspect applications installed or available for selection, including package names, whether an application is debuggable and the Android version it targets; the source application associated with intercepted connections in VPN mode; certificates in the device's trust store, including user-installed certificates, to recognize Gauntry's certificate; the device's Wi-Fi proxy configuration; network availability and DNS/resolver information; whether Gauntry is exempt from battery optimization; and the device's boot count for time-integrity protection. This information is used for local functionality as applicable and is not, solely by being inspected, uploaded to the developer. Gauntry does not intentionally access contacts, location, phone number, IMEI, or advertising ID for these purposes.

## 3. Storage and security

The application saves its traffic and testing records in an **encrypted local SQLCipher database** with a randomly generated passphrase protected through Android Keystore. Captured request and response body files are encrypted individually. Gauntry's locally generated certificate authority (CA) private key is also encrypted using an Android Keystore-protected key. Some settings and the exported **public** CA certificate are not encrypted. Information viewed or copied outside the application may no longer be protected by Gauntry's local encryption.

Gauntry is configured to disable Android cloud backup and exclude app data from Android device-to-device transfer. It has not been verified whether every manufacturer-specific transfer tool honors those exclusions. Android Keystore keys generally cannot be transferred with encrypted app data, potentially making transferred data unreadable on another phone.

Gauntry does not set an automatic age-based deletion schedule or storage quota for captured records. Storage may grow until you remove data or the application is removed. The app's protective storage controls reduce exposure but do not guarantee protection against every device compromise or recovery method.

## 4. Network activity and third parties

**Testing traffic.** Captured connections are forwarded to destinations requested by you or by the applications you deliberately route through Gauntry. You may also send test or replay requests to selected hosts. Destination servers, DNS resolvers, and network providers can observe information ordinarily exposed by those communications. Gauntry's in-app browser also communicates with the sites you visit. These are inherent functions of the product and should not be confused with Gauntry uploading your saved capture database to the developer.

**Local proxy.** The capture proxy is designed to listen on the phone's loopback interface, not on the local Wi-Fi network. Testing confirmed other devices on the tested network could not connect. Other applications on the **same phone** can connect to the active local proxy without a proxy password; traffic they direct through it may be captured. Take care when enabling it.

**Embedded browser and platform services.** The Test Browser uses Android's WebView technology. It presents websites with a browser User-Agent that can disclose the phone model, Android version, firmware build and browser version, and indicate use of an in-app browser. Gauntry disables application-level Google Safe Browsing in its browser views, but testing found Google Play services activity associated with Safe Browsing/SafetyNet when the browser started, and observed browser-engine configuration and statistics activity. Whether Android or Google components transmitted related information to Google was not measured. Gauntry cannot promise that the embedded browser never involves Google or other operating-system services. Websites have their own privacy practices.

**Other components.** The app does not deliberately download fonts through its emoji component. On-device testing did not detect such a download at startup, although independent system font-provider traffic was not measured.

## 5. Beta expiration and trusted-time verification

Each beta build contains a **fixed expiration date and time established at build time**. The expiration does not begin at installation, first launch, or acceptance of the EULA. Gauntry shows the build's expiration in the device's local time in its About/Settings and expiration screens. Installing late leaves less time to use active testing features. No number of days is guaranteed. If an incorrectly advanced device clock makes a build appear expired, correcting the clock and successfully verifying the actual time may restore active functionality, provided the fixed expiration date has not passed. An online time check **does not** renew or extend the installed build; continued active testing beyond the embedded date requires a separately issued newer build with a later expiration date, if any is made available.

Gauntry uses a small trusted-time record in private application storage. It contains a trusted timestamp and clock-integrity information such as elapsed time since boot, boot count, and the source of the trusted time. This record is encrypted using an Android Keystore key, remains on the device, and is not transmitted during verification. A suspect device clock may trigger a warning and restrictions to prevent clock changes from extending access. If the record is unreadable or current time cannot be established, active features may be disabled until a successful online check confirms the installed build has not expired.

When the date cannot be reliably established and the phone is connected to a network, Gauntry **automatically attempts** an online time check whenever the app is opened or brought back to the foreground. A user may also select **"Check again"** on the expired-build or cannot-verify-date screens. This control is not offered solely because the clock is marked suspect. For each attempted check, Gauntry sends a minimal HTTPS **HEAD** request to a public website, reads the server's response date, and stops at the first usable response. The currently configured sequence is `www.cloudflare.com`, `www.apple.com`, `www.microsoft.com`, then `www.google.com`. The list may change with later builds, and multiple hosts may be contacted if preceding ones fail. The request does not intentionally include cookies, account information, device or installation identifiers, captured traffic, or stored results. The contacted host can still see the public IP address, TLS/network connection attributes, and that a request occurred, and may retain logs under its own policy. DNS resolution may also involve the device's configured resolver. Gauntry's own beta-time logging in tester builds is restricted to non-identifying counts, rather than contacted hostnames or server timestamps.

When a build expires or time cannot be verified, active traffic capture, interception, network testing and related operations are restricted. Available functions include viewing previously saved data, applicable deletion controls, legal/privacy text, expiration status, and time verification. Expiration does not itself erase stored data.

## 6. In-app Test Browser data

The embedded browser maintains a local browser profile in the application's private storage that can include cookies, local and session storage, site databases, cached resources, browsing history, saved sign-in information and form data. This information may **persist after closing the browser and restarting Gauntry**. It is not automatically cleared when the browser closes.

The **Clear browser data** control is available from the Test Browser's menu and from the restricted screen displayed after beta expiration or when time cannot be verified. It asks for confirmation; cancellation does not clear the information. When confirmed, it clears cookies, web storage (including local and session storage), browser cache, browser-managed saved credentials and form data, and the browsing history maintained by the browser view being cleared. When invoked from the restricted screen after expiration or inability to verify the date, the history-clearing operation applies to that screen's short-lived browser view; a separate Test Browser session that remains open may retain its in-memory back/forward history until that session closes. Testing verified that previously set cookies were absent after clearing and restarting the application.

**Not every type of site data is necessarily removed.** Testing found that a service-worker cache remained after the operation, and other site-managed resources may also remain. The feature does not securely overwrite storage or guarantee permanent, complete, or forensically unrecoverable deletion. The control **does not remove captured requests, responses or other records in Gauntry's encrypted traffic database**. Those are handled separately as described below.

## 7. Data retention and deletion limitations

Gauntry provides history-clearing and certain item-deletion actions. In the present implementation, these actions generally **soft-delete database rows**, meaning that records are marked deleted and are no longer displayed in the relevant interface, but the underlying encrypted database may still contain transaction metadata, URLs, headers, credentials, and other retained fields. Related encrypted body files are ordinarily deleted from the filesystem using normal file-deletion operations, not securely overwritten. A user's deletion of one item may not remove separate copies kept for testing/replay features.

Some information, such as saved authorization-test runs/results and project records, does not currently have a general in-app deletion control. A full database reset is available only when the database cannot be opened; it is not an ordinary, always-available delete-all button. In that recovery state, resetting removes the database and body files, but it does not remove all other Gauntry material, such as CA material, local settings, or the trusted-time record. The recoverability of deleted information from the underlying phone storage has not been established.

Android ordinarily removes application-private data when app data is cleared or the app is uninstalled, but the exact outcomes have not been verified on a spare device. **A Gauntry CA public certificate that you installed into Android's user trust store may remain after uninstalling the app** and may require separate removal through Android settings. Files copied to other apps, the clipboard, screenshots, screenshots in recent-app previews, or files saved outside Gauntry remain subject to the destination's behavior, not Gauntry's local deletion features.

## 8. Copying, sharing, screenshots and notifications

Gauntry does not currently provide an export feature for its saved traffic database. However, users can select and copy request details, headers, replay requests, and other text, including sensitive data, into other applications through the Android clipboard. Credentials are not necessarily masked. The app does not block screenshots, screen recordings, or recent-app thumbnails, which may display sensitive testing material.

Gauntry can export or share its **public CA certificate** for installation. It does not export the corresponding CA private key. An exported copy of the public certificate may remain in the app's cache.

On one tested Android phone and its current notification settings, the proxy notification displayed the listening port but not visited websites; VPN operation displayed the system VPN key icon. Notifications and lock-screen presentation may differ by device and settings. System-originated messages are not wholly controlled by Gauntry.

## 9. Application logging

In beta builds intended for testers, Gauntry's own diagnostic log messages are designed not to contain destination hostnames, website addresses, HTTP request details, or detailed exception text. Errors are logged by category. A source-code build check is intended to prevent reintroducing sensitive values into the app's own log statements. Developer builds may include more detailed logs.

This restriction does **not** guarantee that the Android operating system, WebView engine, crash traces, or third-party system components never generate diagnostic information revealing browsing or network details. Such behavior was not exhaustively measured in a tester release build. Ordinary device and system logging may be accessible under Android's own controls.

## 10. Who can access data and user responsibility

Gauntry does not operate a cloud repository for your captured traffic and does not send its saved encrypted database to the developer as part of its normal operation. Network destinations and public time-check hosts receive only the communications described above. Device owners, other applications receiving copied content, administrators of a managed device, and parties with appropriate device access may be able to see information depending on permissions and security protections.

You are responsible for ensuring you have permission to capture, inspect, store and transmit the traffic and information involved in your tests, and for complying with applicable confidentiality, privacy and data-preservation requirements. Avoid saving or sharing credentials and other sensitive information unnecessarily.

## 11. Children and intended users

Gauntry is designed for authorized cybersecurity testing rather than use by children. It currently does not include a child-directed feature, age-verification system, or Gauntry user-account registration. Do not use the product to collect children's information without the authorization and legal basis required by applicable law.

## 12. Changes and contact

We may revise this Privacy Policy when the application's features, data handling, or legal requirements change. Material changes will be presented as appropriate before use of the affected beta functionality. The version shown above identifies this first external-beta policy; earlier internal drafts were not distributed to external testers.

For privacy questions, contact **hacken@hacken4u.com**.

**END OF PRIVACY POLICY**
