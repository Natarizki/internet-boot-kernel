# Internet Boot Kernel (IBK)

IBK is a Linux-based internet boot environment intended to start on a PC, establish network connectivity (including Wi-Fi where supported), and retrieve a Linux distribution installer over HTTPS.

## Current prototype

The first prototype is being built from the Archiso baseline. It uses the standard Arch Linux kernel and initramfs; it is not a custom Linux kernel or a completed distribution installer.

The initial live environment is intended to provide:
- Legacy BIOS and UEFI boot through GRUB
- x86_64 Linux kernel and initramfs
- NetworkManager-based Wi-Fi connection
- HTTPS downloads with mandatory SHA-256 verification in the `ibk fetch` command

The x86_64 Archiso GRUB profile is also intended to generate an IA32 UEFI boot entry for compatible x86_64 systems. This needs real hardware testing before being considered supported.

## Planned next steps

1. Produce and validate the first bootable ISO.
2. Test BIOS, UEFI x64, and IA32 UEFI boot paths.
3. Verify Wi-Fi operation on target hardware.
4. Add a maintained distribution catalog, beginning with Fedora.
5. Verify installer metadata and images using trusted checksums or signatures.

## Build

GitHub Actions builds the ISO from the profile in this repository and uploads it as the `internet-boot-kernel-iso` workflow artifact. A successful workflow run is required before an ISO can be considered available.

## Security

The `ibk fetch URL SHA256 FILE` command accepts HTTPS URLs only and rejects the download if the supplied SHA-256 digest does not match. The digest must come from a trusted release source.

## Status

Early development. Bootability, Wi-Fi compatibility, and installer handoff are not yet validated on physical hardware.
