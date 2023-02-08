# Mac

## Tips

- Mac 更改某个拓展名的打开方式，不是 option+submenu，那样只能修改指定文件，**要在 Info 里面的 Open With 设置 为 Change All**.

- iTerms 解决 option + key 无法使用: Use Profiles -> Keys -> Presets to **Natural Text editing**. 然后 remove 原先的设置，不要保留。

- Oh My ZSH Plugins Clones: `git clone https://github.com/<author_name>/<repo_name>.git $ZSH_CUSTOM/plugins/<repo_name>`

## Shell

```
# Disable the "Are your sure you want to open this application?" dialog
defaults write com.apple.LaunchServices LSQuarantine -bool false

# Disable the crash reporter
defaults write com.apple.CrashReporter DialogType -string "none"

###############################################################################
# Trackpad, mouse, keyboard, Bluetooth accessories, and input                 #
###############################################################################

# Increase sound quality for Bluetooth headphones/headsets
defaults write com.apple.BluetoothAudioAgent "Apple Bitpool Min (editable)" -int 40

###############################################################################
# Energy saving                                                               #
###############################################################################

# Enable lid wakeup
sudo pmset -a lidwake 1

# Restart automatically on power loss
sudo pmset -a autorestart 1

# Restart automatically if the computer freezes
sudo systemsetup -setrestartfreeze on

# Sleep the display after 15 minutes
sudo pmset -a displaysleep 15

# Disable machine sleep while charging
sudo pmset -c sleep 0

# Set machine sleep to 5 minutes on battery
sudo pmset -b sleep 5

# Set standby delay to 24 hours (default is 1 hour)
sudo pmset -a standbydelay 86400

# Never go into computer sleep mode
sudo systemsetup -setcomputersleep Off > /dev/null

# Hibernation mode
# 0: Disable hibernation (speeds up entering sleep mode)
# 3: Copy RAM to disk so the system state can still be restored in case of a
#    power failure.
sudo pmset -a hibernatemode 0

# Remove the sleep image file to save disk space
# sudo rm /private/var/vm/sleepimage
# Create a zero-byte file instead…
# sudo touch /private/var/vm/sleepimage
# …and make sure it can’t be rewritten
# sudo chflags uchg /private/var/vm/sleepimage

###############################################################################
# Screen                                                                      #
###############################################################################

# Re-enable subpixel antialiasing
defaults write -g CGFontRenderingFontSmoothingDisabled -bool FALSE

# Require password immediately after sleep or screen saver begins
defaults write com.apple.screensaver askForPassword -int 1
defaults write com.apple.screensaver askForPasswordDelay -int 0

# Save screenshots to the desktop
# defaults write com.apple.screencapture location -string "${HOME}/Desktop"

# Save screenshots in PNG format (other options: BMP, GIF, JPG, PDF, TIFF)
# defaults write com.apple.screencapture type -string "png"

# Disable shadow in screenshots
# defaults write com.apple.screencapture disable-shadow -bool true

# Enable subpixel font rendering on non-Apple LCDs
# Reference: https://github.com/kevinSuttle/macOS-Defaults/issues/17#issuecomment-266633501
defaults write NSGlobalDomain AppleFontSmoothing -int 1

# Enable HiDPI display modes (requires restart)
# sudo defaults write /Library/Preferences/com.apple.windowserver DisplayResolutionEnabled -bool true


######################################################
# Keyboard & Input				     #
######################################################

# Enable full keyboard access for all controls
# (e.g. enable Tab in modal dialogs)
defaults write NSGlobalDomain AppleKeyboardUIMode -int 3

# Turn off keyboard illumination when computer is not used for 5 minutes
defaults write com.apple.BezelServices kDimTime -int 300


###############################################################################
# Finder                                                                      #
###############################################################################

# Avoid creating .DS_Store files on network or USB volumes
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true
defaults write com.apple.desktopservices DSDontWriteUSBStores -bool true

# Expand the following File Info panes:
# "General","Open With", and "Sharing & Permissions"
defaults write com.apple.finder FXInfoPanesExpanded -dict General -bool true OpenWith -bool true Privileges -bool true

# Disable the warning when changing a file extension
defaults write com.apple.finder FXEnableExtensionChangeWarning -bool false

###############################################################################
# Dock                                                                        #
###############################################################################

# Automatically hide and show the Dock
defaults write com.apple.dock autohide -bool true

# Make Dock icons of hidden applications translucent
defaults write com.apple.dock showhidden -bool true


```

## useful Command

Installation

```
# sudo softwareupdate -i -a
xcode-select --install
```

> xattr -d com.apple.rootless <application_locations> //取消文件或文件夹的 SIP 保护状态

## brew

### Need to install

- rmtrash
- bat
-
-

## Need settings

> SIP

-
-

## Software

- yabai [yabai installation](<https://github.com/koekeishiya/yabai/wiki/Installing-yabai-(latest-release)>)
- MonitorControl
- Rectangle
- alt-tab-macos
-
-

## Shell

- https://github.com/zsh-users/zsh-completions
- https://github.com/zsh-users
- [starship](https://github.com/starship/starship)
- https://github.com/Eugeny/tabby
- [alacritty - Recommend Fast Rust Terminals](https://github.com/alacritty/alacritty) !!!
- https://github.com/warpdotdev/Warp
- https://wezfurlong.org/wezterm/install/macos.html

## Dotfiles

- https://github.com/webpro/awesome-dotfiles
- https://driesvints.com/blog/getting-started-with-dotfiles
- https://www.abdullah.today/encrypted-dotfiles/
- https://github.com/webpro/dotfiles ！！！
- https://github.com/lra/mackup
- https://www.chezmoi.io/
- https://github.com/driesvints/dotfiles
- https://github.com/mathiasbynens/dotfiles
- https://github.com/alrra/dotfiles
-

## Command Line

- [The Art of Command Line](https://github.com/jlevy/the-art-of-command-line/blob/master/README-zh.md)
- [awesome macOS Command Line](https://git.herrbischoff.com/awesome-macos-command-line/about/)
- https://zellij.dev/ Tmux 和 screen 替代品
-
-
-

## Recommand Read

- (Yu tools list - Softare etc. Recommand!)[https://github.com/pseudoyu/yu-tools]
- [Terminal Setting article by pseudoyu](https://sspai.com/post/74216)
- Yabai https://sspai.com/post/73620
- https://sspai.com/post/77485
- [我是如何学习一门新的知识 以区块链为例 是落拓呀](https://www.bilibili.com/read/cv6209820)
- [ClearURLs Docs](https://docs.clearurls.xyz/1.23.0/) 可以在 ublock 这些插件里面添加规则替代这个
-
-

## Other Link

- https://www.libhunt.com/topic/macos
- https://www.pseudoyu.com/zh/2022/07/10/my_config_and_beautify_solution_of_macos_terminal/
-
-
