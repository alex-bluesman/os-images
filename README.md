# Existing images:

### Linux

Yocto build revision `yocto-4.2.3` for AArch64 architecture. It contains the following artefacts:
1. `Image` - Linux kernel. Changes added on top:
  * Built-in bootargs: `root=/dev/ram0 rw mem=512M console=ttyAMA0 console=hvc0 earlycon`
2. `qemuarm64.dt*` - QEMU AArch64 device tree. Changes added on top:
  * Disable PCIe, because it's uses I/O regions in high address spaces (0x1040000000) what requires to extend default supported address space in Saturn
  * Add information about initial RAM disk
3. `core-image-minimal-qemuarm64.cpio.gz` - root filesystem image produced by Yocto
