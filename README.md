# DS9 FLATPAK

This repo contains recipie to install DS9 as a flatpak.

This will be helpful for people on rolling release but still want stability when it comes to work.

This is based on `epassaro/ds9-flatpak`.

## Installation

```bash
# Clone the repository
$ git clone https://github.com/amanasci/ds9-flatpak.git && cd ds9-flatpak

# Install flatpak-builder
$ sudo apt install flatpak-builder

# Add the Flathub repository
$ flatpak remote-add --user --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo

# Install the runtime and SDK
$ flatpak install --user flathub org.freedesktop.Platform//22.08 org.freedesktop.Sdk//22.08

# Build the package
$ flatpak-builder --force-clean build_dir com.github.SAOImageDS9.SAOImageDS9.yml

# Install the package
$ flatpak-builder --user --install --force-clean build_dir com.github.SAOImageDS9.SAOImageDS9.yml

# Run the package
$ flatpak run com.github.SAOImageDS9.SAOImageDS9
```

## Desktop Entry

```bash
# Create .desktop file 
nano ~/.local/share/applications/com.github.SAOImageDS9.SAOImageDS9.desktop

# Add following content and save
[Desktop Entry]
Name=SAOImage DS9
Comment=Astronomical Imaging and Data Visualization Tool
Exec=flatpak run com.github.SAOImageDS9.SAOImageDS9
Icon=com.github.SAOImageDS9.SAOImageDS9
Terminal=false
Type=Application
Categories=Education;Science;Astronomy;


#Refresh Desktop database

update-desktop-database ~/.local/share/applications


```
