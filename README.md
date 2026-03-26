# PulseView

Package PulseView and sigrok-cli as a Flatpak.

## Permissions

The package requests these permissions by default:

- `share=network` for connecting to network-based instruments.
- `socket=x11`, `socket=wayland` and `socket=fallback-x11` for X11 and Wayland access
  - You can disable `socket=wayland` to force PulseView to run in X11 mode, which may improve the dragging performance of the cursor tool
- `device=all` for devices with serial interface, etc.
- `allow=bluetooth` for connecting to Bluetooth/BLE enabled multimeters
  - You may wish to disable this if you run into performance issues during device scan

Standard permissions requested by the KDE SDK are also requested.

## Invoking sigrok-cli

You can run the bundled `sigrok-cli` with the following command:

```sh
flatpak run --command=sigrok-cli org.sigrok.PulseView --help
```

Additionally, you can define an alias in your shell so the program can be directly invoked by only typing `sigrok-cli`:

```sh
alias sigrok-cli='flatpak run --command=sigrok-cli org.sigrok.PulseView'
```
