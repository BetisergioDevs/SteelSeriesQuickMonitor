# SteelSeries Quick Monitor

A lightweight Windows notification-area application for monitoring battery level and active DPI on the **SteelSeries Rival 3 Wireless Gen 2**.

> **Independent project:** This application is not affiliated with, endorsed by, or sponsored by SteelSeries.

![SteelSeries Quick Monitor logo](assets/SteelSeriesQuickMonitor-Logo.png)

## Features

- Shows the mouse battery percentage in the Windows notification area.
- Displays the currently active DPI stage.
- Reads DPI over HID. DPI changes remain controlled by the mouse's physical button.
- Refreshes battery information periodically and supports manual refresh.
- Starts hidden in the notification area.
- Tray menu to open the window, refresh battery information, manage Windows startup, or exit.
- Optional Windows startup.
- WPF interface for Windows.

## Compatibility

- Windows 10/11, x64.
- Verified with SteelSeries Rival 3 Wireless Gen 2 using its USB receiver in 2.4 GHz mode.
- Other SteelSeries devices and Bluetooth mode have not been verified.

## Repository status

The public repository has been created and currently contains the project documentation, MIT license, ignore rules, and application logo.

**The application source tree, installer script, bundled `rivalcfg` dependencies, and downloadable setup package have not yet been published.** They will be added after the final working project files have been uploaded and checked. There is no published release yet.

## Download and installation

Once a release is available:

1. Open the repository's **Releases** page.
2. Download `SteelSeriesQuickMonitor-Setup.exe`.
3. Run the installer and follow the setup wizard.
4. The application starts in the notification area. Double-click its tray icon to open the window.

## Build from source

The source code and Inno Setup script will be added to this repository before the build instructions are considered complete.

The intended publish command for the Windows x64 self-contained build is:

```powershell
dotnet publish .\src\SteelSeriesQuickMonitor\SteelSeriesQuickMonitor.csproj -c Release -r win-x64 --self-contained true /p:PublishSingleFile=false
```

The installer is built with Inno Setup 6. The application also relies on the `tools/rivalcfg` files included in the project.

## Disclaimer

Device communication details may vary by mouse model and firmware. The application is intended to read status information; it does not provide controls to write DPI settings to the mouse. Use it at your own discretion.

## Licensing

The original project code is distributed under the MIT License; see [LICENSE](LICENSE). Third-party tools and dependencies retain their respective licenses and notices.
