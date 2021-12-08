# oh-my-zsh-config
My personal ZSH configuration.

## Requirements

 To use this repository, you have to install the following softwares.

 * **[Git](https://git-scm.com/)**
 * **[cURL](https://curl.se/)**

## **Installation and configuration**

To use this configuration, you have to follow some steps and configure your local environment.

 ### **Installing Zsh**
 
 To install Zsh use the command bellow:

 ```
 sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
 ```

 After install Zsh all configurations and environment variables will be placed at `~/.zshrc` so the `~/.bash_profile` won't be used anymore.

**IMPORTANT:** Make sure you have *cURL* installed in your local machine.

### **Firacode font**

This project uses the *Spaceship* theme, and *firacode* has a lot of icons used by this theme, so before install the theme we need to make sure the font is installed.

 * First you have to download the .zip from the latest release of the font [here](https://github.com/tonsky/FiraCode/releases).
 * Extract the zip and install, each system has a different way to install, normally on debian distributions, you can open the fonts inside the folder `TTF` and double clik on each file to install.

### **Spaceship theme**

Now with zsh and font configured, you may want to install the *Spaceship* theme. This theme is really useful for devs who wants to see the versions of Node, Docker, etc.

First you have to clone the theme repository locally:

```
git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"
```

Now, create a new symbolic link between the theme and the folder **theme** from zsh.

```
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
```

Then you just to set the theme on your *.zshrc* file.

```
ZSH_THEME="spaceship"
```

### **Plugins configuration**

Plugins can be very useful and zsh allows to install it, the repository has reference to some, and before using the config, be sure you have the plugin tool installed.

First you have to download and install *ZInit*

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/zdharma/zinit/master/doc/install.sh)"
```

After the installation, your .zshrc will have the following line:

```
### End of ZInit's installer chunk
```

And bellow this line you can paste the lines:

```
zinit light zdharma/fast-syntax-highlighting
zinit light zsh-users/zsh-autosuggestions
zinit light zsh-users/zsh-completions
```

## **Troubleshooting**

Troubleshooting section.

### How to set zsh as default terminal for my user?

Execute the command bellow and restart your computer.
```
sudo usermod --shell $(which zsh) $USER
```

