# Project Post-Mortem: Galaxy M21 Custom ROM Migration

## 1. Executive assessment

The supplied narrative describes an attempt to replace Samsung's stock Android distribution on a Galaxy M21 (SM-M215F) with an unofficial Evolution X 15.0 build. It reports an installer success message and a usable daily-driver outcome.

The report is a useful starting log, but it is not yet a verified engineering post-mortem: exact firmware, device codename, ROM source/maintainer, recovery URL, vbmeta checksum, boot logs, functional tests, before/after measurements, and rollback evidence are missing.

**Assessment:** installation success is reported; stability, compatibility, performance gains, and security-state changes remain unverified.

## 2. Claim-by-claim review

| Original claim | Assessment | Evidence needed |
|---|---|---|
| “Fully stable” / “production deployed” | No defined test period or results supplied. | Uptime, reboot cycles, logs, feature matrix. |
| “0% brick rate” | One handset cannot establish a population-level rate. | If true, say “no brick observed on this unit during the documented period.” |
| Knox Guard/KG bypassed | A successful flash does not prove this. | Reliable state evidence and legitimate ownership/provisioning context. |
| Clock rollback + OTA clears Prenormal | Not a universal or guaranteed method; behavior varies. | Reliable model/firmware-specific documentation. |
| Null-signature vbmeta disables AVB completely | Too absolute; effects depend on image and boot chain. Security integrity may be weakened. | Artifact provenance, checksum, maintainer instructions. |
| TWRP 3.7.1 supports M21 | Version number alone does not prove compatibility. | Exact build URL, maintainer, codename, checksum, firmware base. |
| Installer says success | Shows at most that the installer reported success. | Successful boots and functional tests. |
| Zero ambient telemetry | Unsupported absolute claim. Apps, Google components, ROM services, and network services may communicate. | Defined network-measurement method, duration, endpoints, limitations. |
| Large RAM/latency improvement | No measurements supplied. | Controlled before/after tests and raw data. |

## 3. Technical narrative by phase

### Phase A — Bootloader unlocking

The report mentions Developer Options, USB debugging, OEM unlocking, and Download Mode. USB debugging is generally for Android Debug Bridge; it is not itself the same as bootloader unlocking. OEM unlocking availability and confirmation behavior vary by firmware and device state.

**Improve the log:** record exact model/firmware and the device's displayed unlock state. Do not publish personal identifiers.

### Phase B — KG / Prenormal state

The time-change and OTA-registration sequence is not supported by evidence in the supplied notes. Document it as an unverified observation, not a dependable bypass technique. For enterprise, carrier, financing, or anti-theft restrictions, resolve status through the legitimate owner, seller, carrier, or Samsung support.

### Phase C — Verified Boot and recovery

The report describes flashing vbmeta and a custom recovery, then using a hardware-key sequence to enter recovery. Exact behavior varies by device and firmware. Modifying Verified Boot can reduce integrity guarantees; it is not simply a performance optimization.

Record each image's source, checksum, target model/codename, and the recovery maintainer's instructions. Do not infer success solely from Odin reporting PASS.

### Phase D — Data formatting and ROM installation

Formatting data is destructive and can remove encryption metadata and user files. Installation requirements vary by build and may depend on firmware, recovery, format-data steps, or a prescribed installation order.

Record the ROM release URL, checksum, build date, required firmware, install log, first-boot result, and whether recovery can access storage after reboot. Review logs for personal identifiers before publishing.

## 4. Results and impact

The only outcome supported by the supplied text is that the author reports an installer success message and a usable device. The following remain unproven:

- Repeated successful Android 15 boots without bootloops.
- Working calls, SMS, mobile data, Wi-Fi, Bluetooth, GPS, cameras, biometrics, sensors, USB, charging, and sleep/wake.
- Improved RAM usage, UI latency, or battery life.
- Zero telemetry or complete removal of OEM security controls.
- No data corruption or hardware damage over a meaningful observation period.

Use [VALIDATION.md](VALIDATION.md) to convert these claims into testable statements.

## 5. Risks and lessons

- Wrong model/artifact can cause boot failure or lost functionality.
- Firmware mismatch can cause bootloops.
- Data wipes can irreversibly destroy data without verified backups.
- Weakening boot verification can make persistent tampering harder to detect.
- Unverified downloads can be malicious or corrupt.
- Unsupported claims reduce engineering credibility.

## 6. Portfolio-ready summary

> Documented a custom-ROM migration study for a Samsung Galaxy M21 (SM-M215F), covering bootloader state, recovery and Verified Boot concepts, data-formatting risks, compatibility validation, and rollback planning. Installation was reported successful; stability, feature compatibility, performance gains, and security-state changes remain unverified pending test evidence.
