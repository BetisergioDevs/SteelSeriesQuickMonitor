# SteelSeries Quick Monitor

A lightweight Windows tray application for monitoring battery level and active DPI on the **SteelSeries Rival 3 Wireless Gen 2**.

> This is an independent, community project. It is not affiliated with, endorsed by, or sponsored by SteelSeries.

![SteelSeries Quick Monitor logo](assets/SteelSeriesQuickMonitor-Logo.png)

## Features

- Shows the mouse battery percentage in the Windows notification area.
- Displays the currently active DPI stage.
- Reads DPI directly from the mouse over HID; DPI changes remain controlled by the mouse's physical button.
- Refreshes battery information periodically and supports manual refresh.
- Starts minimized to the notification area.
- Tray menu to open the window, refresh battery information, manage Windows startup, or exit.
- Windows startup option.
- Lightweight WPF interface.

## Compatibility

- Windows 10/11, x64.
- .NET 8 Windows desktop runtime is bundled in the published self-contained build.
- Hardware support currently targets SteelSeries Rival 3 Wireless Gen 2 (USB receiver / 2.4 GHz mode).

Other SteelSeries devices and Bluetooth mode have not been verified.

## Download and installation

1. Open the repository's **Releases** page.
2. Download the latest `SteelSeriesQuickMonitor-Setup.exe`.
3. Run the installer and follow the setup wizard.
4. The application starts in the notification area. Double-click its tray icon to open the window.

If no release is available yet, the installer has not been published.

## Build from source

Requirements:

- Windows 10/11 x64
- .NET 8 SDK
- Inno Setup 6 (only needed to build the installer)

Publish the application:

```powershell
dotnet publish .\src\SteelSeriesQuickMonitor\SteelSeriesQuickMonitor.csproj -c Release -r win-x64 --self-contained true /p:PublishSingleFile=false
```

The installer script is `SteelSeriesQuickMonitor.iss`. Update its `PublishDir` definition if your project is in a different location, then compile it with Inno Setup Compiler.

The `tools/rivalcfg` files required by the application must be present in the project as configured by the project file.

## Disclaimer

This project uses device communication details that may be specific to the listed mouse model and firmware. Use it at your own discretion. The application is intended to read status information; it does not provide controls to write DPI settings to the mouse.

## License

Distributed under the MIT License. See [LICENSE](LICENSE).
