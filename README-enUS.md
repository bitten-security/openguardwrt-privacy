Privacy Policy — OpenGuardWRT
Last updated: August 30, 2026
Also published as a page at: https://bitten-security.github.io/openguardwrt-privacy/

[OpenGuardWRT](https://github.com/bitten-security/OpenGuardWRT) is a read-only dashboard for your own OpenWrt router and AdGuard Home instance. This document explains, plainly, what data the app handles.

Summary
OpenGuardWRT has no server of its own, collects no data, uses no analytics, has no ads, and shares nothing with third parties. The app only talks to the router address you configure yourself, on your local network or over a tunnel/VPN you set up yourself.

What data the app handles

* Router and AdGuard Home login credentials (username and password you enter on the connection screen): stored only on your device, encrypted inside the Android Keystore (via `flutter_secure_storage`). Never sent to any server other than the router/AdGuard Home you configured, and never in plain text outside that direct communication.
* Data shown on the dashboard (connected devices, traffic, DNS status, etc.): read directly from your router on each screen and kept only in the app's memory while you use it — nothing is sent anywhere outside your router/network.
* App lock (PIN/biometrics), if you enable it: uses Android's own biometric authentication (`local_auth`). The app only receives a "yes/no" from the operating system — it never has access to your fingerprint or face.
* App preferences (theme, language, display settings): saved locally on the device.

What the app never does

* No user account or sign-up.
* Never sends data to any server of ours — because none exists.
* No analytics, tracking, ad SDKs, or telemetry of any kind.
* Never shares data with third parties.
* Never reads or stores the DDNS password/credential fields or the ACME certificate fields configured on your router — even though the app is read-only, these two specific fields are deliberately skipped by the app.

Bufferbloat Test
The "Test" button on the Bufferbloat Test loads, inside the app itself (in a WebView), the page of an external provider of your choice — [LibreQoS](https://test.libreqos.com/) or [Waveform](https://www.waveform.com/tools/bufferbloat). The measurement itself runs entirely on those providers' own servers, against your device's internet connection — OpenGuardWRT takes no part in the measurement, it only displays their page. Check each provider's own privacy policy if you use this test.

Android permissions used

* Internet: required for the app to connect to your router's/AdGuard Home's address.
* Biometrics (optional, only if you enable the app lock): used exclusively to unlock the app itself on your device.

No other permission (camera, location, contacts, storage, etc.) is requested.

Contact
Questions about this policy: [joaopbit@proton.me](mailto:joaopbit@proton.me)
