# Gauntry beta

## What Gauntry is

Gauntry is an Android app for testing mobile apps and APIs. It sits between an app and the network, records the HTTP and HTTPS requests that pass through it, and lets you pause, edit, replay and analyze them. Traffic capture, inspection, analysis, and storage are performed locally on the phone. Network requests are transmitted to their intended destinations as part of authorized testing.

## Status

This is a time-limited beta. It is not the finished product.

All features in this beta are available without charge. Features, functionality, and usage limits may change during beta testing and in any later release. If Gauntry is commercially released, some features available for free during the beta may be offered only in paid tiers. No future release or pricing structure is guaranteed.

- Version: 0.9.0-beta.1
- Released: 9 November 2026
- Expiration date and time: 6 January 2027, 23:59:59 (UTC-08:00), which is 7 January 2027, 07:59:59 UTC

Each beta build has a fixed expiration date and time, set when the build is made. See [How the beta expiry works](#how-the-beta-expiry-works).

## Who it is for

Gauntry is for security testers and developers who test mobile apps and APIs.

**Use Gauntry only on apps, devices and systems that you own or are authorized to test.** Captured traffic can include passwords, tokens, cookies and personal data belonging to you or to others. Do not capture data without authorization. The [Beta Testing End User License Agreement](EULA.md) sets out the full terms.

Gauntry asks you to record who each engagement is for and what was authorized before any traffic is intercepted.

## Requirements

- An Android phone running Android 12 or later.
- Permission to install apps from outside the Play Store on that phone.
- A Wi-Fi network, for capture through the proxy. (VPN capture also works on mobile data. See the feature guide.)

## Download and install

**Beta Testing Distribution:** Gauntry is available exclusively to individuals authorized by hacken4u to participate in the beta testing program. Authorization may be granted individually or through an invitation extended to members of designated online communities, including selected Discord servers or channels. Individual registration, identification, or separate approval is not required for members covered by an authorized group invitation.

Authorization to participate does not permit redistribution of the application or sharing its installation package with others. Each tester must obtain Gauntry through a distribution channel designated by hacken4u and affirmatively accept the Beta Testing End User License Agreement before using the application.

The designated distribution channel is the Releases page of this repository. Eligible testers may access that page directly or through a link provided by hacken4u or a community administrator authorized by hacken4u to distribute the beta invitation.

1. Open the [Releases](../../releases) page of this repository.
2. Download the APK for the build you want. Each release lists its SHA-256 value.
3. Check the file before you install it. Compute the SHA-256 of the downloaded APK and compare it with the value in the release. They must match exactly. If they do not, delete the file and do not install it.
   - Linux: `sha256sum <file>`
   - macOS: `shasum -a 256 <file>`
   - Windows: `certutil -hashfile <file> SHA256`
4. Copy the APK to the phone if needed, then open it.
5. Android will ask you to allow installs from the app you used to open the file (for example your browser or file manager). Allow it for that app, then install.

   Samsung Galaxy phones: Samsung's Auto Blocker may prevent installation of apps downloaded outside official app stores. If Auto Blocker blocks the Gauntry APK, first verify that it was downloaded from the official repository Releases page and that its SHA-256 matches the published value. Then, if you choose to proceed, open Settings > Security and privacy > Auto Blocker and temporarily turn off Auto Blocker to complete the installation. Turn Auto Blocker back on immediately afterward. Disabling Auto Blocker temporarily reduces device security protections. Menu names may vary by device and One UI version.

6. Open Gauntry.

### What to expect on first start

1. **The agreement screen.** Gauntry shows the Beta Testing End User License Agreement. You can also open the Privacy Policy from there. Tap **I Agree** to continue, or **Decline**.
   - If you decline, nothing is saved and Gauntry cannot be used. You can tap **Review again** or **Close**.
   - If a later build includes a changed agreement, Gauntry shows it again and asks you to accept it.
2. **Notifications.** After you accept, Android may ask whether Gauntry can post notifications. The proxy uses a notification while it is running.
3. **New project.** Gauntry asks for a project name, client name, scope notes and authorization date. All four fields are required. Tap **Create project**.

### Updating to a newer beta build

Install the newer APK over the one you have. Android only accepts an update with a higher build number. Installing a compatible newer build over the existing installation is designed to preserve locally stored data. However, data preservation is not guaranteed in every circumstance. Do not uninstall the existing application before updating if you need to retain its stored information.

## How the beta expiry works

- **Each build has a fixed expiration date and time.** They are set when the build is made. They do not start counting when you install or first open the app, so installing late leaves you less time.
- **Where to see it.** Setup, then About, shows "This beta build stops capturing on" followed by the expiration date and time in your phone's local time zone (with its offset from UTC), and the same moment in UTC. The agreement screen and the beta-ended screen show it too.
- **Nothing extends a build.** To keep testing after the expiration date and time, install a newer beta build when one is released.

### The date check

Gauntry keeps its own note of the date, so changing the phone's clock does not extend the beta.

- **If your phone's clock is behind** the last time Gauntry saw, Gauntry shows a banner and uses the later time. Check the date and time in Settings.
- **If Gauntry cannot read its note of the date**, it shows **"Gauntry could not check the date"**.
  - This can happen after a save that did not finish, or after the app was restored from a backup.
  - Connecting to the internet allows Gauntry to attempt verification against a trusted time source. If verification succeeds and the installed build has not expired, the restriction is removed. If verification fails or the build has genuinely expired, active testing remains unavailable.
  - Gauntry checks the date with a trusted server by itself when you open the app, or when you tap **Check again**.
  - If the phone's clock is wrong, fix the date and time in Settings first, then go online.
- **What the online check sends.** It is a short request to a public website (for example a large technology company's homepage) to read the current date. It does not send your captured traffic or any account or device identifier. The [Privacy Policy](PRIVACY.md), section 5, lists the sites and exactly what is sent.
- **"Check again"** appears on the "could not check the date" screen and on the "beta has ended" screen.
  - If the check succeeds and the build is still within its dates, Gauntry shows "The date is checked" and you can tap **Continue**.
  - If the check succeeds but the build has expired, Gauntry shows "Gauntry checked the date with a trusted server. This beta has ended."
  - If the check fails, Gauntry says so and nothing is changed.

### When the beta ends

At the expiration date and time, Gauntry shows **"This beta has ended"**.

- **Capture is off.** This build no longer captures or forwards traffic. The date check can still run when you tap Check again.
- **Your data.** Previously captured data remains available for review after expiration. Available data-removal controls remain accessible, subject to their limitations. Clearing history removes records from the application's visible history but does not necessarily permanently erase the underlying encrypted database records. See [Privacy Policy](PRIVACY.md) Section 7.
- **View stored data** opens it. Expiration does not itself erase stored data.
- **Still available:** Clear browser data, the Legal documents, and Check again.
- **If your phone's date was set ahead by mistake**, fix it in Settings, then tap **Check again**.
- **To keep testing**, install a newer beta build.

## Quick start

This gets HTTPS traffic from one app into Gauntry, using the proxy over Wi-Fi.

1. **Open Capture.** Tap the status card at the top of **Traffic**, or tap **Open Capture** in Setup.
2. **Install the Gauntry CA certificate.** Gauntry needs its own certificate to read HTTPS traffic. In the CA certificate block on Capture:
   1. Tap **Save** and save the certificate (`gauntry-ca.pem`) into **Downloads**.
   2. Open Settings, then Security and privacy, then More security settings, then Install from phone storage.
   3. Choose "CA certificate", tap "Install anyway", then authenticate.
   4. In the file picker, choose **Downloads** as the source, not "My Files". On Samsung (One UI) phones the installer rejects the certificate if the source is left on My Files, even after you authenticate.
   5. Select the certificate file, then tap Done.

   The block then reads "CA certificate installed". You only do this once per install.
3. **Start the proxy.** On Capture, tap **Start Proxy**.
4. **Point the phone's Wi-Fi at the proxy.** Capture shows "Set this phone's Wi-Fi proxy to" with a hostname and port.
   - Tap **Wi-Fi Settings**, read the warning, then set a manual proxy for your Wi-Fi network with those values.
   - Make sure the proxy is running first. If it is not, all network traffic on that Wi-Fi will fail.
5. **Check it works with the Test Browser.** Open it from the Traffic screen, load an `https://` page, and look for the requests in Traffic.
6. **Choose an app that will accept the certificate.** On Capture, tap **"Which apps will accept this CA?"**. The Cooperative apps list shows installed apps that are likely to work. Open one of them and use it, and its requests appear in Traffic.
7. **When you are finished,** set the Wi-Fi proxy back to None and tap **Stop Proxy**.

## Feature guide

In roughly the order you will meet them.

**Projects.** Every engagement starts with a project: name, client, scope notes and authorization date. Setup shows the current project's details. This beta keeps one project. It cannot be renamed, switched or deleted from the app yet.

**Capture.** Capture controls how traffic reaches Gauntry, in two ways:
- **Proxy:** Start Proxy and Stop Proxy, the port, and the Wi-Fi proxy instructions. The port can be changed while the proxy is stopped.
- **VPN capture:** routes the apps you choose through Gauntry without changing Wi-Fi settings, and also works on mobile data. It captures only apps that honor the system proxy. Connections that try to go around it are refused and counted.

Capture also holds the CA certificate block, which shows whether this install's certificate is installed. It also reports leftover certificates with the same name from earlier installs.

**Cooperative apps.** A searchable list of installed apps that Gauntry believes it can intercept, with the reason for each. It is advice only: it does not filter traffic. Reach it from "Which apps will accept this CA?" on Capture.

**Traffic.** The list of captured requests for the current project.
- Tap a row to open it and see the request and response headers. Bodies are not shown there yet; to view or edit a request body, send the request to Repeater.
- Long-press a row to hide or exclude that host, or to send the request to Repeater.
- The status card at the top shows whether the proxy and the VPN are running.
- **Clear History** removes this project's history.

**Intercept.** A switch on Traffic, labelled "Intercept is on" or "Intercept is off". It is off every time the app starts.
- While it is on, requests pause until you forward or drop them.
- A banner and a count on Traffic show how many items are paused.
- Open a paused item to edit its headers, then tap **Forward** or **Drop**.
- Header values can be edited, but bodies are read-only.

**Test Browser.** A built-in browser that sends its requests through the Gauntry proxy, so you can check capture without another app.
- Open it from the Traffic screen.
- It uses the proxy, not the VPN, so start the proxy first.
- It checks whether the CA certificate is installed before it loads a page, and tells you if it is not.
- Leaving the screen keeps the page and its state. **Close** ends the session.
- Its menu has **Clear browser data**, which removes cookies, site storage and the cache from the Test Browser and signs you out of the sites you used in it. Some site data, such as service worker caches, may remain.
- Autofill is turned off in the Test Browser.

**Test Browser cache (Setup).** A switch in Setup, in the Test Browser section. It is off by default. Disabling the browser cache helps ensure that ordinary network requests reach the proxy. Some requests may still be handled by service workers or other browser mechanisms without reaching Gauntry, and therefore may not appear in Traffic.
- While it is on, cached requests are never sent and will not appear in Traffic.
- Turning the cache off does not delete what is already cached. Use Clear browser data for that.
- Intercept always keeps the cache off.

**Noise Filter.** Android and Google Play Services can generate frequent background network traffic. Some of that traffic may pass through Gauntry and appear in captured transactions. The Noise Filter lists hosts that are forwarded without ever pausing. It starts with a list of common platform hosts.
- **Hide** keeps recording the traffic but stops showing it. Traffic has an option to show filtered hosts.
- **Exclude** stops recording it at all.

Open the Noise Filter from Setup, or long-press a row in Traffic.

**Repeater.** Edit a captured request and send it again, in tabs. Each tab keeps a history of what you sent and lets you compare responses.
- Send a request to Repeater from a transaction or from a paused item.
- Repeater's own requests do not appear in Traffic, and the Noise Filter does not apply to them.

**Analyze.** One place for the analysis tools:
- **API Mapper:** a map of everything captured: hosts, path templates and operations per method, with status codes and how often authentication was seen. It is also on the Traffic toolbar.
- **JWT Analysis:** decode a JSON Web Token from a captured request, edit its payload, and send the result to Repeater. It is opened from a transaction, not from Analyze: open a row in Traffic, then use its **Decode JWT** action. The key icon appears when the request carries a token.
- **Authorization Testing:** replay one captured request as several identities and compare the responses, to check whether an endpoint enforces authorization. Gauntry reports when two identities received equivalent responses. It does not decide for you whether that is a vulnerability.

**Setup.** The current project, the Noise Filter, a pointer to Capture, the Test Browser cache switch, About, and a short "What's coming" list.

**About and Legal.** About shows the app version and the expiration date and time of this beta build. **Legal** opens the agreement and the Privacy Policy, read-only. Legal is also on the beta-ended screen.

## Known limitations

- **Cooperative apps only.** Gauntry can read HTTPS only from apps that trust a user-installed certificate. Many apps do not. In general that means:
  - your own test apps;
  - apps whose network security settings opt in to user certificates;
  - apps built for very old Android versions;
  - debug builds, but only if they declare a debug network security override.
- **Certificate pinning is not bypassed.** An app that pins its certificates refuses Gauntry's certificate, and its HTTPS traffic cannot be read.
- **QUIC and HTTP/3 are not visible.** Gauntry captures HTTP/1.1 over TCP. If a site loads but nothing appears in Traffic, this may be why.
- **HTTP/2 is downgraded.** Intercepted connections are made to use HTTP/1.1. WebSockets are not supported.
- **Private or self-signed server certificates are not supported.** Gauntry checks the real server against the phone's built-in trusted certificates only. A server using a private, internal or self-signed certificate fails.
- **The proxy needs Wi-Fi.** A Wi-Fi proxy does not exist on mobile data. Use VPN capture for mobile data.
- **A Wi-Fi proxy affects the whole connection.** While it is set, apps that do not trust the Gauntry certificate cannot load HTTPS. Android's own connectivity check is one of them, so the network may report "no internet".
- **VPN capture only sees apps that honor the system proxy.** An app that ignores it is not captured. Its attempts are refused and counted, but cannot be tied to a named app.
- **Test Browser:**
  - Script-heavy web apps may show a blank page even when capture is working.
  - A site's service worker, and possibly pages restored with Back or Forward, can answer without reaching the proxy.
  - Clear browser data may leave service worker caches behind.
  - The browser tells sites the phone model, Android version and firmware build in its User-Agent.
- **Transaction Detail:** Displays request and response headers, but does not yet display their bodies. To view or edit a request body, send the request to Repeater.
- **Paused requests and responses:** Header values can be edited, but bodies are read-only.
- **Body display formats:** JSON and hexadecimal views are not yet available. Brotli-compressed bodies are not decoded for display; gzip and deflate are supported.
- **Body size limit:** Requests and responses containing bodies larger than 10 MiB are refused and not recorded.
- **Traffic export:** Exporting captured traffic is not yet supported. The application's CA certificate can be exported.
- **Deleting is not permanent erasure.** Clearing history removes items from view. The Privacy Policy, section 7, explains what remains on the phone.
- **Not built yet:** a rules engine, findings tracking, and editing of paused request and response bodies. Request bodies can already be edited in Repeater.

These limitations may be addressed in later builds. No future build or feature is guaranteed.

## Privacy in brief

The [Privacy Policy](PRIVACY.md) is the authority. In short:

- **No account, ads or analytics.** Gauntry has no account or login, advertising, in-app analytics, crash-reporting service or cloud sync.
- **Encrypted on the phone.** Captured traffic and testing records are stored on the phone in an encrypted database.
- **No export.** Gauntry has no feature for exporting its saved traffic database. Text you copy out of the app is no longer protected by it.
- **What leaves the phone:** the traffic you choose to route or send, the sites you open in the Test Browser, and the short date check described above. Android, the browser engine and Google services can also be involved; see section 4 of the policy.
- **The proxy stays on the phone.** It listens on the phone itself, not on your Wi-Fi network. Other apps on the same phone can use it while it is running.

## Legal

- [Beta Testing End User License Agreement](EULA.md), version 1.0, SHA-256 `f4ecb4015943894abc3d4bd92ce1522cb29a26e390f7b5a32928690407d84939`
- [Privacy Policy](PRIVACY.md), version 1.0, SHA-256 `cc0684117e8f8876ed78101d1c1a2257eabddf97a9d202fb9862106a19a89683`

These files are identical to the copies bundled in the app.

## Feedback

Use [GitHub Issues](../../issues) and pick a template: **Bug report** or **Feedback**.

Please include:
- the Gauntry version from Setup, then About;
- your Android version and phone model;
- what you did, what happened, and what you expected.

**Do not include** captured traffic, tokens, passwords, API keys, session cookies, customer data or any other personal data. Describe the problem instead. Issues on this repository are public.

To report a security problem, follow [SECURITY.md](SECURITY.md) instead of opening a public issue.

## Changes

See [CHANGELOG.md](CHANGELOG.md).

## Licence

All rights reserved. Use of the app is governed by the Beta Testing End User License Agreement.
