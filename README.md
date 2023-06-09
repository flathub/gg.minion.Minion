# Minion 3
Flatpak wrapper for Minion, a premier addon manager.

## Disclaimer (important to read)

### Regarding Hardware Acceleration

As hardware acceleration doesn't work well with XWayland under Wayland with the closed-sourced Nvidia drivers, hardware acceleration was disabled to have higher coverage for GPUs.

One may enable hardware acceleration by running `flatpak override --user --device=dri gg.minion.Minion`. Be wary, this will cause flickering for Minion if you're using the proprietary Nvidia driver while running Wayland.

### First start

After running minion for the first time while there are AddOns already installed in a newly-added game folder, minion will seem frozen. After a restart Minion will start working again and the issue shouldn't occur anymore.

## Addon snapshots

Minion doesn't support backups of AddOns with system links as they will appear blank. Using the direct path ex. `~/.var/app/com.valvesoftware.Steam/...` will work.

## Information about the project
This version of Minion is using Java. As it requires JavaFX and it's not provided by OpenJDK it was settled to use [Bellsoft Liberica JRE 11](https://bell-sw.com/pages/downloads/) as it provided all the needed libraries.

It is also compatible with a flatpak installation of ESO through flatpak Steam and hopefully Lutris.

## Installing (preffered way)

The preffered way to install Minion is to install it via flathub. To add flathub to your system you need to run:

```bash
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

After that Minion can be installed:

```bash
flatpak --user install gg.minion.Minion
```

And ran with:

```bash
flatpak run gg.minion.Minion
```

## Building and runnning

Building:

    flatpak-builder --user --install --force-clean build-dir gg.minion.Minion.yml

Bulding in a silverblue toolbox container:

    flatpak-builder --user --install --force-clean build-dir gg.minion.Minion.yml --disable-rofiles-fuse

Checking Minion version for updates:

    flatpak run org.flathub.flatpak-external-data-checker gg.minion.Minion.yml

Running:

    flatpak run gg.minion.Minion

## Screenshots

### Showing installed addons
![installed](./screenshots/installed.png)

### Showing available addons for download
![find](./screenshots/find.png)


### Searching for addons
![search](./screenshots/search.png)

### Backup
![backup](./screenshots/backup.png)

### Archived Backup
![archived backup](./screenshots/archived-backup.png)