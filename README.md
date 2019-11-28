# awesome-dotfiles

![](/screenshot.png)

## Contents ##
1. [Details](#details)
2. [Dependencies](#dependencies)
3. [Installation](#installation)
4. [Application Theming](#appTheming)
5. [Folder Structure](#folderStructure)

<a name="details"></a>
## Details ##
- **OS**: Arch Linux
- **Shell**: ZSH
- **WM**: awesome
- **Theme**: Adwaita-dark
- **Icons**: McMojave-Circle-Blue-Dark
- **Terminal**: Alacritty

<a name="dependencies"></a>
## Dependencies ##
|Dependency|Description|Why|
|:----------|:-------------:|:------:|
|`awesome-git`|Window manager - **must use git version**|The WM these dotfiles are built around|
|`compton-tryone`|Window compositor|Screen tearing sucks and transparenct blurry windows are cool|
|`rofi`|Application launcher|used to launch applications|
|`feh`|Image viewer, used to set background|Sets background|

<a name="installation"></a>
## Installation ##
1. Ensure all [dependencies](#dependencies) are met
2. Clone this repository and place its contents into your `.config` folder
3. navigate to the `awesome` folder and place your desired wallpapers into the `wallpaper` folder, ensuring that you follow the naming conventions
4. edit the `apps.lua` file to define your desired default and startup applications
5. optional: edit the `keys.lua` file to change / add keybinds. Please refer to the [Folder Structure](#folderStructure) section of the readme to learn about how the file structure is laid out

<a name="appTheming"></a>
## Application Theming ##
### Firefox ###
1. [Set up My Custom Firefox Theme](https://github.com/willpower3309/MinimalistMaterialFox)
2. Use [this](https://github.com/Jaredk3nt/homepage) homepage

### Spotify ###
1. [Install `Spicetify`](https://github.com/khanhas/spicetify-cli)
2. chown spotify directory: `sudo chown $USER -R /opt/spotify`
3. run `spicetify` once to generate config
4. `spicetify backup apply enable-devtool` to enable devtools
5. Place your color.ini and user.css in `~/.config/spicetify/Themes/<your theme name, whatever you want>` and edit `~/.config/spicetify/config.ini` to reflect this name
6. run `spicetify update restart`

### OhMyZsh ###
- Install Powerline Fonts
  - `git clone https://github.com/powerline/fonts.git`
  - `cd fonts`
  - `./install.sh`
  - set font
- Change theme to agnoster
  -`open ~/.zshrc`
  - Set ZSH_THEME="agnoster" and save the file
- Install Plugins (Note That ~/.zshrc edits are in repo)
  - Syntax Hilighting
    - `git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting`
    - Edit `~/.zshrc`, add `zsh-syntax-highlighting` to the plugins section
    - Reread config `source ~/.zshrc`
  - Autosuggestion
    - `git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions`
    - Edit `~/.zshrc`, add `zsh-autosuggestions` to the plugins section
    - Reread config `source ~/.zshrc`
- [Guide](https://www.freecodecamp.org/news/jazz-up-your-zsh-terminal-in-seven-steps-a-visual-guide-e81a8fd59a38/)

<a name="folderStructure"></a>
## Awesome Folder File Structure ##
In order to avoid a poorly organized rc.lua spanning thousands of lines, it has been split into multiple files / folders.
- `rc.lua`: Contains the script that runs when awesome starts (essentially links all the other files together)
- `apps.lua`: Contains the default and startup applications
- `keys.lua`: Contains keybinds
- `rules.lua`: Contains window rules
- `theme.lua`: Contains theme variables
- `wallpaper.lua`: Contains wallpaper time changing functionality
- `icons`: stores icons used in WM
- `wallpaper`: stores wallpaper
- `components`: Folder that contains all of the components of the WM, such as panels, volume and brightness widgets, notification widget etc
- `widgets`: stores scripts used in the functionality of the components

## Current To-Do ##
- fix spinning cursor bug on adjust volume / brightness (due to components or widgets)
- make adjust volume / brightness more smooth
- finish adding keybinds
- populate side panel
- lock screen
