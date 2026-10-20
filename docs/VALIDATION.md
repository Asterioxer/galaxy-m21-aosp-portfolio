# Post-Install Validation Plan

Mark an item only after performing the test. Record date, build ID, conditions, and concise evidence references.

## A. Identity and provenance

- [ ] Confirm model is SM-M215F in device settings or a trusted device-information screen.
- [ ] Record Android version, ROM build ID, security patch level, kernel version, and build date.
- [ ] Record ROM and recovery release URLs, maintainers, and firmware base.
- [ ] Save checksums for downloaded artifacts.
- [ ] Confirm build explicitly targets this model/codename.

## B. Boot and recovery

| Test | Status | Evidence / notes |
|---|---|---|
| First boot completes | NOT TESTED | |
| Three cold boots complete | NOT TESTED | |
| Five restart cycles complete | NOT TESTED | |
| Recovery can be entered | NOT TESTED | |
| Recovery accesses intended storage | NOT TESTED | |
| No unexpected reboot/bootloop over 7 days | NOT TESTED | |
| Backup and restore path documented | NOT TESTED | |

## C. Hardware and core functions

| Test | Status | Evidence / notes |
|---|---|---|
| SIM and mobile registration | NOT TESTED | |
| Voice calls and SMS | NOT TESTED | |
| Mobile data | NOT TESTED | |
| Wi-Fi and Bluetooth | NOT TESTED | |
| GPS/location | NOT TESTED | |
| Front/rear cameras and video | NOT TESTED | |
| Microphone and speakers | NOT TESTED | |
| Sensors | NOT TESTED | |
| Fingerprint/biometrics, if supported | NOT TESTED | |
| USB data transfer | NOT TESTED | |
| Charging and battery reporting | NOT TESTED | |
| Sleep/wake and idle drain | NOT TESTED | |
| Screen lock and encryption after reboot | NOT TESTED | |

## D. Performance comparison

Compare stock and custom ROM under similar conditions: same apps, network, brightness, temperature range, and battery state. Repeat measurements and report median/range. Record boot-to-unlock time, idle memory use, app launch latency, battery drain over a defined period, and a repeatable workload benchmark. Explain thermal throttling and other confounders.

| Metric | Stock baseline | Custom ROM | Method / conditions |
|---|---|---|---|
| Boot-to-unlock time | Not measured | Not measured | |
| Idle RAM after settling | Not measured | Not measured | |
| App launch latency (median) | Not measured | Not measured | |
| Battery drain over fixed idle interval | Not measured | Not measured | |
| Repeatable workload score | Not measured | Not measured | |

## E. Security and privacy

- [ ] Document bootloader state as displayed by the device.
- [ ] Record reported verified-boot/integrity state without equating it to complete security.
- [ ] Review included Google services and installed apps separately.
- [ ] For telemetry claims, define capture setup, duration, DNS/endpoint visibility, and blind spots.
- [ ] Do not equate AOSP-based with zero telemetry.
- [ ] Do not claim OEM controls are defeated without reliable evidence and relevant context.

## F. Evidence hygiene

Never publish IMEI, serial number, phone number, account email, Wi-Fi credentials, tokens, or private keys. Mask identifiers in screenshots and review logs before sharing.

**Status vocabulary:** PASS (performed and passed), FAIL (performed and failed), BLOCKED (dependency prevented test), NOT TESTED (not performed), INCONCLUSIVE (evidence unclear).
