# 01. Android Studio Installation on Windows 11

## Learning objectives

By the end of this chapter, you should be able to:

- Check whether your computer is suitable for Android development.
- Download Android Studio from the official source.
- Install the IDE using the setup wizard.
- Complete the first-run configuration.
- Open Android Studio and create a project.

## 1. What is Android Studio?

Android Studio is Google's official integrated development environment (IDE) for Android application development. It includes a code editor, project tools, Gradle integration, debugger, profiler, emulator management and tools for building Android packages.

You will use Android Studio to write Kotlin code and develop the AR INFOTEK application.

## 2. Check your computer

Recommended practical configuration:

| Component | Recommended |
|---|---|
| Operating system | Windows 11, 64-bit |
| RAM | 16 GB or more |
| Processor | Modern Intel Core i5 / AMD Ryzen 5 or better |
| Storage | SSD with at least 30 to 40 GB free for IDE, SDK and emulator growth |
| Display | 1920 × 1080 preferred |
| Virtualisation | Enabled for a performant emulator |

Android Studio and the Android Emulator have separate resource requirements. An emulator can consume several gigabytes of RAM. On an 8 GB computer, test on a physical phone when possible and close memory-heavy applications.

Check available RAM:
1. Press `Ctrl + Shift + Esc`.
2. Open Task Manager.
3. Select Performance.
4. Select Memory.

Check free storage:
1. Open File Explorer.
2. Select This PC.
3. Check the free space on the drive you intend to use.

## 3. Download Android Studio

1. Open https://developer.android.com/studio.
2. Select the Windows download.
3. Read and accept the licence terms.
4. Download the installer.
5. Keep the installer in a known folder, such as Downloads.

Download only from the official Android Developers website. Avoid third-party installer sites.

## 4. Install the IDE

1. Run the downloaded `.exe` installer.
2. Approve the Windows permission prompt if displayed.
3. Keep Android Studio selected.
4. Keep Android Virtual Device selected if you plan to use an emulator.
5. Choose the installation location.
6. Complete the installation.
7. Start Android Studio.

The exact installer screens can change between releases. Follow the current wizard rather than relying on an old screenshot.

## 5. First-run setup wizard

1. Choose whether to import previous settings. For a new setup, select the option to start without importing.
2. Select the Standard setup type unless you have a specific reason to customise it.
3. Choose a UI theme.
4. Review the SDK components to be installed.
5. Accept the relevant licences.
6. Allow the downloads to finish.
7. Finish the wizard.

The setup wizard normally installs the SDK components required by the current Android Studio release.

## 6. Verify installation

On the Welcome screen, open More Actions or the relevant SDK Manager entry. Confirm that an Android SDK location is configured.

Open Android Studio and check that:
- The Welcome screen appears without an installation error.
- SDK Manager opens.
- Device Manager opens.
- Android Studio can check for updates.

## 7. Common installation problems

### Installer does not start
- Right-click the installer and choose Run as administrator if permitted.
- Check Windows security software quarantine history.
- Download the installer again from the official site if the file may be incomplete.

### Setup downloads fail
- Check internet connectivity.
- Check whether a proxy or firewall blocks Google download hosts.
- Retry the failed component in SDK Manager.

### Insufficient disk space
- Free disk space before installing.
- Keep project files, SDK files and Gradle caches in planned locations.
- Do not delete SDK folders while Android Studio is using them.

## Practical assignment

1. Install Android Studio.
2. Open the IDE.
3. Open SDK Manager and Device Manager.
4. Record the Android Studio version and SDK location.
5. Take a screenshot of the Welcome screen.

## Knowledge check

1. What is an IDE?
2. What is Android Studio used for?
3. Why does an emulator require additional memory?
4. Where should you download Android Studio?
5. What is the purpose of the setup wizard?

## Completion criteria

You can open Android Studio and access SDK Manager and Device Manager without errors.

## Official reference

https://developer.android.com/studio
