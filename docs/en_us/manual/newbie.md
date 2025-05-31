# Getting Started

- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
    - [1. Confirm System Version](#1-confirm-system-version)
    - [2. Install Runtime Environment](#2-install-runtime-environment)
      - [Windows](#windows)
      - [Other Systems (Linux, macOS)](#other-systems-linux-macos)
        - [Linux](#linux)
        - [macOS](#macos)
        - [Additional dependencies for the graphical user interface (MFAAvalonia) (applicable to Linux and macOS)](#additional-dependencies-for-the-graphical-user-interface-mfaavalonia-applicable-to-linux-and-macos)
    - [3. Download the Correct Version](#3-download-the-correct-version)
      - [Windows](#windows-1)
      - [macOS](#macos-1)
      - [Linux](#linux-1)
      - [Android](#android)
    - [4. Extract Correctly](#4-extract-correctly)
    - [5. Confirm Emulator Support](#5-confirm-emulator-support)
    - [6. Set Emulator Resolution Correctly](#6-set-emulator-resolution-correctly)
    - [7. Pip settings (Windows)](#7-pip-settings-windows)
  - [Related Documentation](#related-documentation)

## Prerequisites

### 1. Confirm System Version

M9A on Windows only supports Windows 10 and 11. For older Windows versions, please refer to the system issues section in the [FAQ](FAQ.md#runtime-library-issues) (Note: Original link points to MAA docs, adapt if needed).

> [!WARNING]
>
> The following content originates from MAA and differs from M9A, so it's for reference only.
> [PlayCover is temporarily not supported](https://github.com/MaaXYZ/MaaFramework/issues/405).

If you are using MacBook with Apple Silicon, please go to [this page](https://maa.plus/docs/zh-cn/manual/device/macos.html#apple-silicon-%E8%8A%AF%E7%89%87) (Note: Original link points to MAA docs).
M9A also supports Macs with [Intel chips](https://maa.plus/docs/zh-cn/manual/device/macos.html#intel-%E8%8A%AF%E7%89%87) (Note: Original link points to MAA docs), but we would rather recommend you to install Windows on your Mac and use the Windows version of M9A.

If you wish to use M9A on Android devices, please go to [this page](https://maa.plus/docs/zh-cn/manual/device/android.html) (Note: Original link points to MAA docs).

### 2. Install Runtime Environment

#### Windows

For Windows users:

  1. **VCRedist x64 must be installed**: This is the basic requirement for running M9A (whether it is the command line version or the graphical interface version MFAAvalonia).

     - Click [vc_redist.x64](https://aka.ms/vs/17/release/vc_redist.x64.exe) to download and install.

  2. **If you use the graphical interface (MFAAvalonia), you need to install .NET 8**:

     - It is recommended to visit the [.NET official download page](https://dotnet.microsoft.com/download/dotnet/8.0) and download and install the **.NET Desktop Runtime 8** that is suitable for your system (usually the x64 version).

**Installation via `winget` (recommended)**:
You can also right-click the Windows Start button, select "Command Prompt" or "PowerShell (Administrator)", and then paste the following command in the terminal and press Enter to conveniently install VCRedist x64 and .NET 8 Desktop Runtime at the same time:

```sh
winget install Microsoft.VCRedist.2017.x64 Microsoft.DotNet.DesktopRuntime.8
```

#### Other Systems (Linux, macOS)

##### Linux

**Python Version Dependency**:

- Your system needs to have **Python version ≥ 3.10** installed. This is required for M9A to start and manage its internal environment.
- M9A will automatically create and use an independent virtual environment and install the required Python dependency packages (from `requirements.txt`) when it is run for the first time. You **do not** need to manually create a virtual environment or install these dependencies.

##### macOS

**Python environment**: The macOS version of M9A has a built-in embedded Python environment, so you **do not** need to install or configure Python separately. The program will automatically use this embedded environment and manage its dependencies.

##### Additional dependencies for the graphical user interface (MFAAvalonia) (applicable to Linux and macOS)

If you plan to use the graphical user interface (MFAAvalonia) on Linux or macOS, **you also need to install the .NET 8 runtime**.

- Please visit the [.NET official download page](https://dotnet.microsoft.com/download/dotnet/8.0).
- Select and download and install the appropriate **.NET Runtime** according to your operating system (Linux/macOS) and CPU architecture (e.g. x64, Arm64).

### 3. Download the Correct Version

Download from the [M9A Releases page](https://github.com/MAA1999/M9A/releases).

Chinese Mainland users can also download it at high speed through [MirrorChyan](https://mirrorchyan.com/en/download?rid=M9A).

#### Windows

Usually, download the `M9A-win-x64-<version>.zip` file.

- Unzip the package and run `MaaPiCli.exe`（command line）or `MFAWPF.exe` (GUI), both are OK.

#### macOS

- Checking Processor Type (Important: You must select the correct version for proper operation):

  1. Click the Apple logo in the top-left corner of the screen.
  2. Select "About This Mac".
  3. In the window that appears, you can see the processor information.

- If you are using an Intel X86 processor, please download `M9A-macos-x86_64-vXXX.zip`
- If you are using an Apple Silicon series processor such as M1, M2, etc. with ARM architecture, please download `M9A-macos-aarch64-vXXX.zip`

- Usage:

  1. Open the terminal, decompress the distributed compressed package. It is recommended to decompress it to `usr/local/bin`. It is not recommended to store it in `/opt` to avoid permission issues.

     ```shell
     sudo unzip -o <path to the downloaded M9A compressed package> -d usr/local/bin/M9A
     ```

  2. Continue in the terminal to grant execute permissions to the UNIX executable file:

     ```shell
     cd usr/local/bin/M9A
     # If you manually open the terminal in the root directory of the decompressed software, you can skip the above line.
     sudo ./MaaPiCli
     ```

  3. If you want to use the graphical operation interface, please follow step 2 and execute the `MFAAvalonia` program.
  
#### Linux

Same as MacOS. Download and grant execute permissions to use `MaaPiCli` or `MFAAvalonia`.

#### Android

~~This version is not recommended for general users and has been removed from the release version.~~
If you are very familiar with mobile phone operation, you can refer to the [Usage Method](https://github.com/MaaXYZ/MaaFramework/issues/475) and the [Development Documentation](../develop/Notes-Before-Development.md) to install it yourself.

### 4. Extract Correctly

Extract the entire contents of the downloaded `.zip` file to a folder path that **does not contain any non-English characters or spaces**. For example, `D:\M9A` is good, but `D:\游戏 工具\M9A` is bad.

### 5. Confirm Emulator Support

M9A relies on emulators. Supported emulators are generally listed in the [List of Supported Emulators and Devices](https://maa.plus/docs/zh-cn/manual/device/) documentation. Common choices include MuMu Player 12, LDPlayer 9, BlueStacks 5, NoxPlayer. Ensure your emulator is supported and properly configured.

### 6. Set Emulator Resolution Correctly

The game must run at **1280x720 resolution** inside the emulator. Configure this in the emulator's display settings. Incorrect resolution is a common cause of recognition failures.

>[!WARNING]
>
> Note that after changing the resolution, the simulator homepage should be horizontal (tablet version), do not select vertical (mobile version)!

### 7. Pip settings (Windows)

Content in `config/pip_config.json` :

```jsonc
{
    "enable_pip_update": true, # Whether to enable update pip, default true, recommended to enable
    "enable_pip_install": true, # Whether to enable pip installation, default true, recommended to enable
    "last_version": "v3.2.0", # Read the version of interface.json when pip is installed, compare it with the version when it is started, and try to install it if it is different
    "mirror": "https://mirrors.ustc.edu.cn/pypi/simple", # Mirror source. The parameters after pip install -i can be filled in according to personal needs. Note that users outside the mainland should modify the value to ""
    "backup_mirrors": [
     "https://pypi.tuna.tsinghua.edu.cn/simple",
     "https://mirrors.cloud.tencent.com/pypi/simple/",
     "https://pypi.org/simple"
    ]  ## Backup mirror source
}
```

## Related Documentation

- [Connection Settings](./connection.md): How to configure ADB and connect to the emulator.
- [MaaPiCli Usage Instructions](./MaaPiCli.md)——Introduces the usage of MaaPiCli~~Translation Documentation~~
- [Feature Introduction](./feature.md)——Introduces the precautions for some features
- [FAQ](./faq.md): Solutions to common problems.
- [MirrorChyan Usage Instructions](./MirrorChyan.md)——Introduces the usage of MirrorChyan
