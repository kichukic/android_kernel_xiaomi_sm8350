# Kernel Changelog for Xiaomi SM8350 (Snapdragon 888)

Branch: `17.0-bakasu-susfs`  
Target: `haydn` / `haydnin` / `sm8350`  
Version: Linux 5.4.302-qgki

## 2026-11-05 Release Updates

### Networking & Latency
- **Google BBR TCP Congestion Control:**
  - Enabled `CONFIG_TCP_CONG_ADVANCED=y`
  - Enabled `CONFIG_TCP_CONG_BBR=y`
  - Set `CONFIG_DEFAULT_BBR=y` and `CONFIG_DEFAULT_TCP_CONG="bbr"`
  - Delivers dynamic bandwidth probing, prevents throughput collapse on wireless packet loss, and cuts bufferbloat latency.

### Anti-Reboot & Panic Hardening
- **Panic On Oops Disabled:** `# CONFIG_PANIC_ON_OOPS is not set`
- **Qualcomm Watchdog Bite On Panic Disabled:** `# CONFIG_QCOM_FORCE_WDOG_BITE_ON_PANIC is not set`
- **Subsystem Restart (SSR) Timeout Panic Disabled:** `# CONFIG_PANIC_ON_SSR_NOTIF_TIMEOUT is not set`
- **Panic Timeout Reset:** `CONFIG_PANIC_TIMEOUT=0`
- **Result:** Hardware and subsystem driver glitches recover transparently without crashing or forcing unexpected device reboots.

### Root & Hiding Stack
- **BakaSU 1.5.5:** Next-generation KernelSU implementation with custom preinstalled manager hook (`35257`).
- **SUSFS 1.5.5:** Kernel-level mount and path cloaking to protect Play Integrity and pass strong hardware security checks.

### Peripherals
- **USB Video Class:** Enabled `CONFIG_USB_CONFIGFS_F_UVC=y` for hardware webcam/video output support.
