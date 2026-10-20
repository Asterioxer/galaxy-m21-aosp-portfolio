# Device Compatibility Notes

## Why the exact ROM instructions matter

Samsung Exynos 9611 devices share some platform characteristics, but that does not mean their ROMs share installation procedures, recovery compatibility, or feature support. The exact build maintainer's instructions take precedence over generic guides and guides for other ROM projects.

A public guide for the DragonFox Project's Exynos 9611 ROMs covers the Galaxy M21 alongside other Exynos 9611 models and explicitly warns users not to use TWRP for **that project's ROMs**. It also lists limitations affecting VoLTE/VoWiFi and camera quality. This is useful evidence that recovery choice and hardware support can be project-specific; it is **not proof** that the same restrictions apply to Evolution X 15.0.

Reference: https://github.com/DragonFox-Project/wiki/blob/main/exynos9611/install.md

## Implications for this project

- Do not describe TWRP 3.7.1 as confirmed compatible until the exact Evolution X build's maintainer documentation is located.
- Do not infer that a ROM works fully because it boots; test telephony features, cameras, biometrics, sensors, charging, sleep/wake, and encryption.
- Do not reuse a guide written for another ROM project without confirming the exact device, firmware, recovery, and installation method.
- Add the exact ROM release URL, maintainer, build date, and checksums before claiming reproducibility.

## Current finding

The supplied project report does not identify the exact Evolution X build URL or maintainer instructions. Recovery compatibility and device-specific feature support therefore remain **unverified**.
