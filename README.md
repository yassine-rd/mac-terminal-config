# How to make your boring macOS terminal look so much better

In this repository I'll be sharing exactly how I setup my mac terminal to look amazing and get a much better experience. We'll be using iTerm2, zsh, Oh-My-Zsh, Powerlevel10k as the macOS terminal theme and some other cool plugins!

![Terminal Mockup](https://github.com/yassine-rd/mac-terminal-config/blob/master/images/terminal-mockup.png)

> I do pretty much all of my software development work inside the terminal, so It's important for me to have a pleasant terminal window to look at or work with.

## Install Homebrew

The first thing we want to do is open up a new terminal window and then run the following command to install [Homebrew](https://brew.sh/) which we'll be using as a package manager to download things for our machine.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

After installing, add it to the path (replace "[username]" with your actual username):

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/[username]/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

You can check whether homebrew is correctly installed by running:

```bash
brew --version
```

## Install iTerm2

We're going to use [iTerm2](https://iterm2.com/) which I think is a lot better than the default macOS terminal. To install, run:

```bash
brew install --cask iterm2
```

Switch to iTerm2 for the remainder of this walkthrough.

## Install Git

We want to make sure that we have [Git](https://git-scm.com/) installed. To check you can do:

```bash
git --version
```

I have it installed, but if you don't you can run:

```bash
brew install git
```

## Install Oh My Zsh

We're now going to install [Oh My Zsh](https://ohmyz.sh/) to configure the terminal and make it look nice:

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Install PowerLevel10K theme for Oh My Zsh

```bash
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

Now that it's installed, open the "~/.zshrc" file with your preferred editor and change the value of "ZSH_THEME" as shown below:

```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
```

To reflect this change on your terminal, restart it or run this command:

```bash
source ~/.zshrc
```

## Install Meslo Nerd font

Install the font by pressing "y" and then quit iTerm2.

## Update VS Code terminal font (Optional)

I know a lot of you might be using [VS Code](https://code.visualstudio.com/) so I wanted to point out that once you change the font in the terminal you'll also have to change it in the settings for VS Code terminal by opening up the settings.json file and adding this line:

```json
"terminal.integrated.fontFamily": "MesloLGS NF"
```

## Configure PowerLevel10K

Restart iTerm2. You should now be seeing the [PowerLevel10K](https://github.com/romkatv/powerlevel10k) configuration process. If you don't, run the following:

```bash
p10k configure
```

Follow the instructions for the PowerLevel10K configuration to make your terminal look as desired.

## Increase terminal font size

1. Open iTerm2 preferences
2. Go to Profiles > Text
3. I personally increase my font size to about 16px

## Change iTerm2 colors to my custom theme

1. Open iTerm2
2. Download my color profile by running the following command (will be added to Downloads folder):

```bash
curl https://raw.githubusercontent.com/yassine-rd/mac-terminal-config/main/coolkheey.itermcolors --output ~/Downloads/coolkheey.itermcolors
```

3. Open iTerm2 preferences
4. Go to Profiles > Colors
5. Import the downloaded color profile (coolkheey)
6. Select the color profile (coolkheey)

You can find other themes here: [Iterm2 Color Schemes](https://iterm2colorschemes.com/)

## Install zsh plugins

- Install [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions), a pluging that suggests commands as you type based on history and completions:

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

- Install [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting). It enables highlighting of commands whilst they are typed at a zsh prompt into an interactive terminal. This helps in reviewing commands before running them, particularly in catching syntax errors.

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

- Open the "~/.zshrc" file in your desired editor and modify the plugins line to what you see below:

```code
plugins=(git zsh-autosuggestions zsh-syntax-highlighting web-search)
```

- Load these new plugins by running:

```bash
source ~/.zshrc
```

You're Done!

With that, you're finished and should have a much better looking macOS terminal!
