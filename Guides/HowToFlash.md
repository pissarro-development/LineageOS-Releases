# LineageOS Flashing Guide for Redmi Note 11 Pro+ 5G (pissarro)

## Prerequisites

1. Unlocked bootloader
2. [Android SDK Platform-Tools](https://developer.android.com/tools/releases/platform-tools) (`adb` & `fastboot`) installed and added to PATH on your PC
3. Compatible `boot.img` from release
4. ROM installation `.zip` package from release

---

## Step-by-Step Instructions

### 1. Boot into Fastboot

- Power off your device completely.
- Hold **Volume Down + Power** simultaneously until the Fastboot screen appears, then connect device to your PC via USB.

### 2. Flash Recovery

Flash provided `boot.img` to boot partition:

```bash
fastboot flash boot boot.img
```

### 3. Reboot into Recovery

Wait for process to complete, then reboot into recovery manually or using following command:

```bash
fastboot reboot recovery
```

### 4. Perform a Factory Reset

Once device reboots into recovery, select:

1. "Factory Reset"
2. "Format Data/Factory reset"
3. "Format Data"

### 5. Install ROM package via ADB

In recovery menu, select:

1. "Apply update"
2. "Apply from ADB"

Then on your computer, sideload ROM package using:

```
adb sideload <package>.zip
```

### 6. Reboot into Recovery

After sideload completes, recovery will prompt you to reboot. Select Yes to reboot into new recovery.

### 7. Flash GApps or Modules (optionally)

After rebooting you can flash GApps or Modules (if you wish).

In recovery menu, select:

1. "Apply update"
2. "Apply from ADB"

Then on your computer, sideload ROM package using:

```
adb sideload <package>.zip
```

### 8. Reboot into System

Once installation is complete, return to main recovery menu and select Reboot to system.

### 9. Done

Your device will now boot into system. First boot may take several minutes.

---

## Disclaimer

```
Flashing custom software carries real risk: bootloops, data loss, broken
hardware functionality and, in rare cases, an unrecoverable device.

You are choosing to make these modifications. Neither the maintainer of this
project nor the authors of the hosted software are responsible for anything
that happens to your device. Read the instructions, verify checksums, and
make backups.
```