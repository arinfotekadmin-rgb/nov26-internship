# 05. Connect a Physical Android Phone

## Learning objectives

- Enable Developer Options.
- Enable USB debugging.
- Connect a phone to Windows.
- Verify the connection with ADB.
- Run an Android app on the phone.

## 1. Prepare the phone

The exact menu labels vary by phone manufacturer and Android version.

1. Open Settings.
2. Open About phone.
3. Find Build number. On some phones it is under Software information.
4. Tap Build number seven times.
5. Enter the device PIN if requested.
6. Return to Settings.
7. Open Developer options.
8. Enable USB debugging.

Only enable USB debugging on devices you control. Turn it off when you no longer need it, especially before connecting the phone to an untrusted computer.

## 2. Connect the phone

1. Use a USB cable that supports data, not charging only.
2. Connect the phone to the computer.
3. Unlock the phone.
4. Select File transfer if the phone asks for a USB mode.
5. Approve the RSA debugging prompt.
6. If offered, allow the computer only if you trust it.

## 3. Verify using ADB

Open Android Studio's terminal or PowerShell.

```powershell
adb devices
```

If `adb` is not on PATH, run it using the full path to `platform-tools\adb.exe`.

A successful device usually appears with the status `device`.

Possible statuses:

- `device`: connected and authorised.
- `unauthorized`: unlock the phone and approve the debugging prompt.
- No device listed: check cable, USB mode, driver and USB debugging.

## 4. Windows USB drivers

Some manufacturers require a Windows USB driver. Install drivers only from the phone manufacturer's official support website.

For Google devices, use the official Google USB driver where applicable. Many modern phones work with Windows' built-in drivers.

## 5. Run the app

1. Open the Android Studio project.
2. Select the physical phone from the device selector.
3. Click Run.
4. Wait for the app to install and start.

## 6. Troubleshooting

### Device shows as unauthorized
- Unlock the phone.
- Reconnect the cable.
- Accept the RSA prompt.
- If necessary, revoke USB debugging authorisations in Developer Options and reconnect.

### Device is not detected
- Try another data-capable cable.
- Try another USB port.
- Check USB mode.
- Install the correct manufacturer driver.
- Restart the ADB server:

```powershell
adb kill-server
adb start-server
adb devices
```

### App installation fails
- Check available phone storage.
- Check Android version compatibility with the app's `minSdk`.
- Read the Android Studio Run output.

## Practical assignment

1. Connect your phone.
2. Run `adb devices`.
3. Run the starter app.
4. Rotate the phone and observe the layout.
5. Disconnect and reconnect the device.

## Knowledge check

1. How do you enable Developer Options?
2. What does USB debugging allow?
3. What does `unauthorized` mean in ADB?
4. Why should you use a data-capable cable?
5. When should USB debugging be disabled?

## Completion criteria

Android Studio detects your phone and runs the application. If you do not have a phone, document the limitation and complete emulator testing.
