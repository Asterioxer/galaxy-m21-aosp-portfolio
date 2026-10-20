# Safety, Data Handling, and Rollback

## Before modifying a device

- Confirm lawful ownership and resolve seller, carrier, enterprise, financing, or anti-theft restrictions through legitimate channels.
- Verify exact model/codename and read the ROM maintainer's installation instructions from the official release source.
- Back up personal files and verify the backup can be read.
- Record stock firmware version and identify a trusted restoration path for the exact model and region before changing partitions.
- Use reliable cables/ports and keep adequate battery charge.
- Download images only from trusted sources; verify published checksums/signatures.
- Understand unlocking and formatting may erase data and affect warranty, security, DRM, payment apps, or device management.

## Verified Boot and security trade-offs

Android Verified Boot helps detect unauthorized changes to verified partitions. Disabling or weakening verification can reduce tamper detection and expose the device to persistent modification. Treat boot-chain changes as a security trade-off, not a performance tweak.

A custom ROM does not automatically eliminate data collection. Installed apps, Google services, network providers, and ROM services may still communicate.

## Stop conditions

Stop and re-check documentation if the model/codename does not exactly match, artifact provenance/checksum is missing, the device reports an unexpected state, a flash utility fails, or a proposed fix relies on an unverified bypass claim. Do not repeatedly flash random images to troubleshoot an unexplained failure.

## Rollback outline

This is a planning checklist, not a device-specific flashing guide.

1. Keep verified backups off the handset.
2. Identify official or trusted stock firmware for the exact model/region and a reputable restoration procedure.
3. Record the original software build and required host tools/drivers.
4. Preserve ROM/recovery versions and redact logs before sharing.
5. Follow a reputable model-specific restore procedure and verify that the restored system boots and core functions work.
6. Re-check encryption, screen lock, and sensitive accounts after restoration.

A precise rollback procedure cannot be safely written from the supplied report because exact firmware build, region, ROM artifacts, and recovery provenance are missing.
