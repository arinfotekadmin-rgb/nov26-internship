# 04. Android Emulator Setup

## Learning objectives

- Explain what an Android Virtual Device (AVD) is.
- Create an emulator.
- Select a system image.
- Run an app on the emulator.
- Troubleshoot common emulator problems.

## 1. Emulator and AVD

The Android Emulator runs a virtual Android device on your computer. An Android Virtual Device (AVD) is the configuration describing that virtual device, including device profile, Android system image, screen characteristics and other settings.

An emulator is useful when you do not have several physical devices available. It can also test different screen sizes and Android versions.

## 2. Check virtualisation

For good emulator performance, hardware virtualisation should be available and enabled in the computer firmware.

On Windows:
1. Open Task Manager.
2. Select Performance.
3. Select CPU.
4. Check the Virtualization status.

If disabled, check your computer manufacturer's instructions for enabling Intel VT-x or AMD-V in BIOS/UEFI. Menu names vary by manufacturer.

Windows hypervisor components and emulator acceleration support can vary by hardware and Android Studio release. Follow the current emulator setup guide rather than installing multiple hypervisors blindly.

## 3. Create an AVD

1. Open Android Studio.
2. Open Device Manager.
3. Select Add a new device or Create Virtual Device.
4. Choose a phone profile, such as a Pixel profile.
5. Select a recommended system image.
6. Download the image if required.
7. Review the AVD configuration.
8. Finish.

Use a system image compatible with your computer architecture. An x86_64 image is common on supported Intel/AMD Windows systems.

## 4. Start the emulator

1. Open Device Manager.
2. Click the Run icon beside the AVD.
3. Wait for Android to boot.
4. Unlock the virtual device.
5. Select the emulator from Android Studio's device selector.
6. Click Run to install and launch your app.

The first boot may take longer than later starts.

## 5. Emulator settings

You may adjust:
- Device profile and screen size.
- System image / Android API level.
- RAM and storage allocation.
- Orientation.
- Location simulation.
- Network conditions.
- Camera settings.

Do not allocate excessive RAM to the emulator on a low-memory computer.

## 6. Troubleshooting

### Emulator is slow
- Close unnecessary applications.
- Confirm hardware virtualisation is enabled.
- Use an appropriate system image.
- Reduce emulator resource allocation if the host is under pressure.
- Test on a physical phone.

### Emulator does not start
- Read the Device Manager error.
- Check available disk space.
- Update Android Emulator through SDK Manager.
- Check the current Android Emulator troubleshooting guide.

### App does not appear
- Confirm the emulator has finished booting.
- Check the selected run configuration.
- Read the Run and Build output.

## Practical assignment

1. Create one phone AVD.
2. Start it.
3. Run the starter application.
4. Change the emulator orientation.
5. Take a screenshot of the running app.

## Knowledge check

1. What is an AVD?
2. What is a system image?
3. Why does hardware virtualisation matter?
4. Can an emulator replace all physical-device testing?
5. Where can you manage AVDs?

## Completion criteria

You can create an AVD and run the starter app on it.
