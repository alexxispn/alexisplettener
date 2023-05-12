---
author: Alexis Plettener
pubDatetime: 2023-05-12T10:51:52.737Z
title: My Zsh
postSlug: my-zsh
featured: true
ogImage: /assets/my-zsh.png
tags:
  - zsh
  - terminal
  - linux
  - ubuntu
  - shell
  - powerlevel10k
  - oh-my-zsh
description: This is my Zsh configuration.
---

# My Zsh

![My Zsh](/assets/my-zsh.png)

## Introduction

Zsh is a shell designed for interactive use, although it is also a powerful scripting language. Many of the useful features of bash, ksh, and tcsh were incorporated into zsh; many original features were added.

Powerlevel10k is a theme for Zsh. It emphasizes speed, flexibility and out-of-the-box experience.

### Install ZSH

1. Update and Install Zsh:

```bash
sudo apt update && sudo apt install zsh
```

2. Set Zsh as default shell:

```bash
chsh -s $(which zsh)
```

3. Install Curl and Git if they are not installed:

```bash
sudo apt install curl git
```

4. Install Oh My Zsh:

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

5. Install Powerlevel10k theme:

```bash
git clone https://github.com/romkatv/powerlevel10k.git
```

7. Move the theme to the themes folder:

```bash
mv powerlevel10k ~/.oh-my-zsh/themes/
```

8. Install the recommended font MesloLGS NF Regular:

```bash
wget https://github.com/romkatv/dotfiles-public/blob/master/.local/share/fonts/NerdFonts/MesloLGS%20NF%20Regular.ttf
```

9. Set the font in the favorite terminal.

10. Install the recommended plugin zsh-autosuggestions:

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-completions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
git clone https://github.com/agkozak/zsh-z
```

11. Move the plugins to the plugins folder:

```bash
mv zsh-autosuggestions ~/.oh-my-zsh/plugins/ && mv zsh-completions ~/.oh-my-zsh/plugins/ && mv zsh-syntax-highlighting ~/.oh-my-zsh/plugins/ && mv zsh-z ~/.oh-my-zsh/plugins/
```

12. Edit the Zsh configuration file ~/.zshrc and set the following variables:

```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
plugins=(git zsh-autosuggestions zsh-completions zsh-syntax-highlighting zsh-z)
```

13. Restart the terminal and set the Powerlevel10k theme:

```bash
p10k configure
```

OPTIONAL: My personal configuration:

```bash
git clone https://github.com/alexxispn/my-zsh.git
mv my-zsh/.zshrc ~/
```
