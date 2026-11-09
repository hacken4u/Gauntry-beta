# Changelog

## 0.9.0-beta.1 - 9 November 2026

The first externally distributed beta build, offered to invited testing communities. Expiration date and time of this build: 6 January 2027, 23:59:59 (UTC-08:00), which is 7 January 2027, 07:59:59 UTC.

### What's in this build

- **Capture through a local proxy or VPN capture.** VPN capture routes the apps you choose and also works on mobile data.
- **HTTPS capture** for apps that trust the Gauntry CA certificate, with step-by-step install instructions on the Capture screen.
- **The proxy port** can be chosen on the Capture screen.
- **Cooperative apps list:** installed apps that are likely to accept the Gauntry certificate.
- **Traffic, with Intercept.** Pause requests, edit headers, then forward or drop them. Intercept is off every time the app starts.
- **Noise Filter** to hide or exclude background platform traffic.
- **Repeater** to edit and resend captured requests in tabs and compare responses.
- **Analyze:** API Mapper, JWT Analysis and Authorization Testing.
- **Test Browser** with HTTPS, kept open in the background while you work elsewhere in the app.
- **Test Browser cache switch** in Setup, off by default, to help ordinary network requests reach the proxy. Some requests handled by service workers or other browser mechanisms may not appear in Traffic.
- **Clear browser data** for the Test Browser, also available from the beta-ended screen.
- **Privacy settings in the Test Browser:** autofill and Safe Browsing are turned off.
- **Beta time limit:** a fixed expiration date and time per build, with an online date check and a "Check again" button.
- **First-start agreement screen** with the Beta Testing End User License Agreement 1.0 and Privacy Policy 1.0, both readable later from Legal.
- **A new launcher icon.**
- **Requires Android 12 or later.**
