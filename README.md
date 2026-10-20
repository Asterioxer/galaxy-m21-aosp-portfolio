# Galaxy M21 AOSP Revitalization — Engineering Case Study

> **Device:** Samsung Galaxy M21 (SM-M215F) · **SoC:** Exynos 9611 · **Reported target:** Evolution X 15.0 / Android 15  
> **Status:** User-reported installation; independently unverified.

This repository documents a reported custom-ROM migration intended to extend the useful life of a legacy Android handset. It focuses on device compatibility, Android boot-chain concepts, recovery, validation, risk management, and reproducible evidence—not on claiming unverified security bypasses.

## Accuracy and evidence note

The original notes describe the device as “fully stable,” “0% brick rate,” and claim that Knox Guard/KG protections were defeated and telemetry eliminated. Those claims are **not independently demonstrated** by the supplied notes. A successful installer message alone does not prove stable boots, working hardware, disabled security controls, or zero telemetry.

## Device and software inventory

| Item | Reported value | Status |
|---|---|---|
| Handset | Samsung Galaxy M21 (SM-M215F) | User-provided |
| SoC | Exynos 9611, ARM64 | User-provided |
| Target ROM | Evolution X 15.0 unofficial build | Exact build/source not supplied |
| Recovery | TWRP 3.7.1 described as M21-specific | Exact maintainer/build URL not supplied |
| Flash utility | Odin3 v3.14.4 on Windows | User-provided |
| Outcome | Installer success reported | No logs, checksums, or test matrix supplied |

Compatibility is device- and build-specific. Do not assume that an image for a related Samsung model is safe for SM-M215F. See [Device Compatibility Notes](docs/DEVICE_COMPATIBILITY.md) for a project-specific caution: a guide for a different Exynos 9611 ROM project explicitly advises against TWRP for its own builds. That warning cannot automatically be generalized to Evolution X, but it demonstrates why the exact ROM maintainer instructions must be verified.

## Reported workflow

1. Prepare the handset and host tools; record exact model, firmware, battery level, and backups.
2. Unlock the bootloader only where permitted; expect a data wipe.
3. Check the device's OEM/Knox Guard/KG state using documented device status. The reported clock-change/OTA sequence is not a universal or verified method.
4. Use only recovery and ROM builds explicitly intended for the exact model and documented by maintainers.
5. Follow the ROM maintainer's installation order for firmware, recovery, vbmeta, data formatting, and ROM installation; requirements vary by build.
6. First boot and run the validation checklist in [docs/VALIDATION.md](docs/VALIDATION.md).

The original notes mention Odin, vbmeta, TWRP, data formatting, and ROM ZIP installation. Exact artifact sources and checksums were not provided, so this is not a reproducible flashing recipe.

## Engineering lessons

- Confirm model/codename, firmware base, partition layout, and maintainer instructions before flashing.
- Verified Boot is an integrity mechanism; changing it can weaken tamper detection.
- Formatting data can irreversibly destroy files and encryption metadata.
- A successful flash is not a stability result; test repeated boots and core hardware.
- AOSP-derived software does not automatically mean zero telemetry.
- Keep verified backups, artifact provenance, and a rollback plan.

## Repository map

- [Post-mortem](docs/POSTMORTEM.md) — claim-by-claim review and technical analysis.
- [Validation](docs/VALIDATION.md) — post-install test matrix and evidence checklist.
- [Safety and rollback](docs/SAFETY_AND_ROLLBACK.md) — security trade-offs and recovery planning.
- [Device compatibility notes](docs/DEVICE_COMPATIBILITY.md) — why recovery and feature support are ROM-specific.
- [References](docs/REFERENCES.md) — authoritative sources and provenance checklist.
- [Changelog](docs/CHANGELOG.md) — documentation revisions.

## Current status

Documentation draft; device state not independently tested. No ROM binary, recovery image, firmware, proprietary flashing utility, or device-identifying logs are included.

## License

Documentation is provided under the MIT License. This does not grant rights to third-party ROMs, firmware, Samsung software, or flashing tools.
