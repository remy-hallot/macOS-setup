# macOS Setup

## Rosetta (only for Intel applications on Apple Silicon Mac)
For installing [Rosetta](https://support.apple.com/fr-fr/102527) run the following command in a terminal:

```bash
softwareupdate --install-rosetta --agree-to-license
```

## Xcode Command Line Tools
For installing [Xcode](https://developer.apple.com/xcode) command line tools run the following command in a terminal:  

```bash
xcode-select --install
```

## Homebrew
For installing [Homebrew](https://brew.sh) run the following command in a terminal:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Homebrew is installed in `/opt/homebrew` on Apple Silicon, which is not in the `PATH` by default. Add it by running the following commands:

```bash
echo >> ~/.zprofile
echo 'eval "$(/opt/homebrew/bin/brew shellenv zsh)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv zsh)"
```

## Upgrade Bash version
For upgrading [Bash](https://www.gnu.org/software/bash) version run the following command in a terminal:  

```bash
brew install bash
```

## Upgrade Rsync version
For upgrading [rsync](https://rsync.samba.org) version run the following command in a terminal:  

```bash
brew install rsync
```

## Bash Completion
For installing [Bash Completion](https://github.com/scop/bash-completion) run the following command in a terminal:  

```bash
brew install bash-completion@2
```

To activate it in Bash, add the following line to `~/.bash_profile`:

```bash
[[ -r "$HOMEBREW_PREFIX/etc/profile.d/bash_completion.sh" ]] && . "$HOMEBREW_PREFIX/etc/profile.d/bash_completion.sh"
```

## Find
For installing [Find](https://www.gnu.org/software/findutils) run the following command in a terminal:  

```bash
brew install findutils
```

## Make
For installing [Make](https://www.gnu.org/software/make/) run the following command in a terminal:  

```bash
brew install make
```

GNU Make is installed as `gmake`. To use it as `make`, add the following line to `~/.zprofile`:

```bash
PATH="$HOMEBREW_PREFIX/opt/make/libexec/gnubin:$PATH"
```

## Tree
For installing [Tree](https://oldmanprogrammer.net/source.php?dir=projects/tree) run the following command in a terminal:  

```bash
brew install tree
```

## cURL
For installing [cURL](https://curl.se) run the following command in a terminal:  

```bash
brew install curl
```

macOS already provides cURL, so Homebrew does not add its own to the `PATH`. To use it instead of the macOS one, add the following line to `~/.zprofile`:

```bash
PATH="$HOMEBREW_PREFIX/opt/curl/bin:$PATH"
```

## Wget
For installing [Wget](https://www.gnu.org/software/wget) run the following command in a terminal:  

```bash
brew install wget
```

## jq
For installing [jq](https://jqlang.org) run the following command in a terminal:  

```bash
brew install jq
```

## tldr
For installing [tldr](https://tldr.sh) run the following command in a terminal:  

```bash
brew install tlrc
```

## iTerm2
For installing [iTerm2](https://iterm2.com) run the following command in a terminal:  

```bash
brew install --cask iterm2
```

## Oh My Zsh
For installing [Oh My Zsh](https://ohmyz.sh) run the following command in a terminal:  

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Zsh plugins
For installing the [Zsh](https://www.zsh.org) plugins [zsh-completions](https://github.com/zsh-users/zsh-completions) and [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions) run the following commands in a terminal:  

```bash
brew install zsh-completions
brew install zsh-autosuggestions
```

Zsh refuses to load completions when their parent directory is group-writable, so remove this permission:

```bash
chmod go-w "$HOMEBREW_PREFIX/share"
```

Then activate the plugins by adding the following lines at the end of `~/.zshrc`:

```bash
FPATH="$HOMEBREW_PREFIX/share/zsh-completions:$FPATH"
autoload -Uz compinit
compinit

source "$HOMEBREW_PREFIX/share/zsh-autosuggestions/zsh-autosuggestions.zsh"
```

## Git
For installing [Git](https://git-scm.com) run the following command in a terminal:  

```bash
brew install git
```
Setup a .gitignore global using [this](https://www.toptal.com/developers/gitignore/api/macos,phpstorm)

## Composer
For installing [Composer](https://getcomposer.org) run the following command in a terminal:  

```bash
brew install composer
```

## GitHub CLI
For installing [GitHub CLI](https://cli.github.com) run the following command in a terminal:  

```bash
brew install gh
```

## Symfony CLI
For installing [Symfony CLI](https://symfony.com) run the following command in a terminal:  

```bash
brew install symfony-cli/tap/symfony-cli
```

## AWS CLI
For installing [AWS CLI](https://aws.amazon.com/cli/) run the following command in a terminal:  

```bash
brew install awscli
```

## Vim
For installing [Vim](https://www.vim.org) run the following command in a terminal:  

```bash
brew install vim
```

## PHP
For installing [PHP](https://php.net) run the following command in a terminal:  

```bash
brew install php
```

## Sublime Text
For installing [Sublime Text](https://www.sublimetext.com) run the following command in a terminal:  

```bash
brew install --cask sublime-text
```

## PhpStorm
For installing [PhpStorm](https://www.jetbrains.com/fr-fr/phpstorm) run the following command in a terminal:  

```bash
brew install --cask phpstorm
```

## Docker Desktop
For installing [Docker Desktop](https://www.docker.com/products/docker-desktop) run the following command in a terminal:  

```bash
brew install --cask docker-desktop
```

## Bruno
For installing [Bruno](https://www.usebruno.com) run the following command in a terminal:  

```bash
brew install --cask bruno
```

## Node.js
For installing [Node.js](https://nodejs.org) run the following command in a terminal:  

```bash
brew install node
```

## Claude Code
For installing [Claude Code](https://claude.com/product/claude-code) run the following command in a terminal:  

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

Claude Code is installed in `~/.local/bin`. If the `claude` command is not found, add this directory to your `PATH` by running the following commands:

```bash
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

## Codex
For installing [Codex](https://github.com/openai/codex) run the following command in a terminal:  

```bash
curl -fsSL https://chatgpt.com/codex/install.sh | sh
```

## Ollama
For installing [Ollama](https://ollama.com/) run the following command in a terminal:  

```bash
brew install --cask ollama-app
```

## Other Apps

### Rectangle
For installing [Rectangle](https://rectangleapp.com) run the following in a terminal:  

```bash
brew install --cask rectangle
```

### The Unarchiver
For installing [The Unarchiver](https://theunarchiver.com) run the following in a terminal:  

```bash
brew install --cask the-unarchiver
```

### Firefox
For installing [Firefox](https://www.firefox.com) run the following in a terminal:  

```bash
brew install --cask firefox
```

### Google Chrome
For installing [Google Chrome](https://www.google.com/chrome/) run the following in a terminal:  

```bash
brew install --cask google-chrome
```

### Slack
For installing [Slack](https://slack.com) run the following in a terminal:  

```bash
brew install --cask slack
```

### Obsidian
For installing [Obsidian](https://obsidian.md) run the following in a terminal:  

```bash
brew install --cask obsidian
```

### FileZilla
FileZilla for Mac can be downloaded [here](https://filezilla-project.org/download.php?platform=osx).

### VLC
For installing [VLC](https://www.videolan.org) run the following command in a terminal:  

```bash
brew install --cask vlc
```

### Bitwarden
For installing [Bitwarden](https://bitwarden.com) run the following command in a terminal:  

```bash
brew install --cask bitwarden
```

### HandBrake
For installing [HandBrake](https://handbrake.fr) run the following command in a terminal:  

```bash
brew install --cask handbrake-app
```
