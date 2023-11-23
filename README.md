# sgt7 macOS Setup

---

This is my current build process for installing macOS and applications as well as hardening. Currently it is a process of first re-installing macOS and then running the post-install macOS setup script macOSSetup.sh.

This is definitley a work in progress and will be updated as it evolves.

## Relevant sources and links

- [macOS Security and Privacy Guide
  ](https://github.com/drduh/macOS-Security-and-Privacy-Guide)
- [macOS Terminal Shortcuts](https://support.apple.com/guide/terminal/keyboard-shortcuts-trmlshtcts/mac)
- [MacOS Buildout](https://github.com/andrewconnell/osx-install)

## 1. Create a macOS USB installer

Note: There have been reports that M1 Macs have had issues after wiping the Hard Drive. It is highly recommended that you create a USB bootable installer.

Reference: [How to create a bootable installer for macOS](https://support.apple.com/en-us/HT201372)

1. Create a bootable installer for macOS by following the instructions in the aforementioned reference link.

## 2. Re-install macOS

## Apple Silicon Mac

Reference: [Use macOS Recovery on an Apple Silicon Mac](https://support.apple.com/guide/mac-help/macos-recovery-a-mac-apple-silicon-mchl82829c17/mac)

Internet Recovery has been removed. To boot into Recovery mode follow the below procedure.

**Ensure the macOS USB installer is inserted into your Mac.**

1. If powered on shut it down.
2. Power on the Mac, but hold the power button until “Loading startup options” appears.
3. When presented with your Hard Drive (typically Macintosh HD), Install macOS (Version), or Options, select "Install macOS (Version)" and "Continue."
4. Select a user with Administrator access and authenticate and select "Next." Authenticate when prompted.

- Optionally (and preferred), if you are not able to authenticate with a known admin user account or you want to compltely wipe your mac, you can select "Erase Mac..." from the top left menu under Recovery Assistant.

5. From the Recovery menu select Disk Utility.
6. Select the internal disk labeled Macintosh HD. If there's an option title Erase Volume Group, check the box.
7. Select Erase and select "Erase Mac..." when prompted from the dialog.
8. Finally select Erase Mac and Restart.
9. After the Mac reboots select your preferred language on the Language screen.
10. If not automatically activated activate your Mac with your Apple ID. If you do not have an Apple ID one can be created with the following direct link.
    - [Create an Apple ID](https://appleid.apple.com/account)
11. Exit to Recovery.
12. Select Reinstall macOS `Current Version`.
13. Reinstall the OS.

### Intel Mac

Reference: [Use macOS Recovery on an Intel Mac](https://support.apple.com/guide/mac-help/use-macos-recovery-on-an-intel-based-mac-mchl338cf9a8/mac)

**Ensure the macOS USB installer is inserted into your Mac.**

1. Start in Internet Recovery Mode by pressing `Shift ⇧ + Option (or Alt) ⌥++ Command (or Cmd) ⌘ + R` while powering up your Mac.
2. Erase the entire disk via the Disk Manager. (_Otherwise, the system will try to reinstall the OS from the recovery image instead of downloading a clean version from official sources._)
3. Reinstall macOS.

## 3. Execute macOSSetup Script

**Open a terminal**

- On a clean install of macOS, Spotlight is the easiest way to open terminal. Press Command (or Cmd) ⌘ + Space Bar. When presnted with a dialig start to type Terminal and when presented with a match press Enter.

### mas

- [mas cli](https://github.com/mas-cli/mas)

**Installed manually until I can find a better method than Homebrew and other manual processes. I will probably use mas-cli.**

- [Signal](https://updates.signal.org/desktop/signal-desktop-mac-universal-6.35.0.dmg)

**Chrome**

**VScode**

**Microsoft Remote Desktop**

**1Password**

**Firefox**

**VLC Player**

**Acrobat Reader**

**VNC Viewer**

**Draw.io**

**rectangle**

**Manually Installed with Homebrew**

- brew install --cask google-cloud-sdk
  source "$(brew --prefix)/share/google-cloud-sdk/path.zsh.inc"
  source "$(brew --prefix)/share/google-cloud-sdk/completion.zsh.inc"

- Vagrant
  brew install hashicorp/tap/hashicorp-vagrant
  brew install vagrant-vmware-utility

**ASDF Plugins and Packages**
asdf plugin-add terraform https://github.com/asdf-community/asdf-hashicorp.git
asdf plugin-add packer https://github.com/asdf-community/asdf-hashicorp.git
asdf global terraform latest
asdf global packer latest
