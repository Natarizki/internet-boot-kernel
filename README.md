# Internet Boot Kernel (IBK)

IBK is a Linux-based internet boot environment intended to start on a PC, establish network connectivity (including Wi-Fi where supported), and retrieve a Linux distribution installer over HTTPS.

## Project status

Early development. The repository is being initialized; no bootable ISO is available yet.

## Initial target

- x86_64 Linux kernel
- GRUB boot menu for legacy BIOS and UEFI
- Minimal initramfs-based userspace
- Network bring-up and verified HTTPS downloads
- Fedora as the first planned installer target

32-bit UEFI support is a compatibility goal and will be validated separately. A 32-bit UEFI bootloader does not by itself guarantee that a 64-bit kernel can boot on that firmware.

## Security and integrity

Downloaded installer metadata and artifacts must be checked against trusted checksums or signatures before use. The initial prototype must not silently treat an unverified download as valid.

## Build

The GitHub Actions build workflow and implementation scripts will be added as the prototype is developed. Until then, this repository does not produce an ISO.

## License

License: to be decided.
