# khushal-mac-dev-setup

This repository contains my personal MacOS setup and configuration files. It includes scripts and documentation for setting up a new Mac with my preferred tools, applications, and settings.

## Contents

- Development tools installation
- System preferences configuration
- Application settings
- Shell configuration (zsh + iTerm2 + Powerlevel10k)
- Development environment setup

## Prerequisites

- A fresh MacOS installation
- Administrative access
- Internet connection

## Getting Started

1. Clone this repository:
```bash
git clone https://github.com/khushal1198/khushal-mac-dev-setup.git
cd khushal-mac-dev-setup
```

2. Follow the setup instructions in each section below.

## Essential Applications

### 1. Google Chrome
1. Download Chrome from [https://www.google.com/chrome](https://www.google.com/chrome)
2. Install and set as default browser

### 2. 1Password
1. Download 1Password from [https://1password.com/downloads/mac](https://1password.com/downloads/mac)
2. Sign in with existing account to restore passwords

### 3. Homebrew
Install Homebrew (macOS package manager):
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

After installation, follow the instructions in the terminal to add Homebrew to your PATH.

### 4. Git
Install Git using Homebrew:
```bash
brew install git
```

Configure Git:
```bash
git config --global user.name "khushal1198"
git config --global user.email "khushal.pujara@yahoo.com"
```

Restore GitHub SSH key from 1Password and place in `~/.ssh/` directory. Verify the connection:
```bash
ssh -T git@github.com
```

### 5. iTerm2
1. Install iTerm2:
```bash
brew install --cask iterm2
```

2. For iTerm2 configuration, check out my dedicated repository:
[khushal-iterm2-config](https://github.com/khushal1198/khushal-iterm2-config)

### 6. Cursor IDE
1. Download Cursor from [https://cursor.sh](https://cursor.sh)
2. Install and set up with your preferred settings

## Development Tools

### 1. Python 3.11
Install Python 3.11 using Homebrew:
```bash
brew install python@3.11
```

After installation:
- Python 3.11 will be available as `python3.11`
- Pip will be available as `pip3.11`
- Packages will be installed in `/usr/local/lib/python3.11/site-packages`

### 2. Bazel 8
Install Bazelisk (Bazel version manager):
```bash
brew install bazelisk
```

Bazelisk will automatically download and use the latest stable version of Bazel (currently 8.2.1). If you need a specific version, you can:
1. Create a `.bazelversion` file in your project:
```bash
echo "8.2.1" > .bazelversion
```
2. Run Bazel commands normally - Bazelisk will manage the version for you

If `bazel` command is not found after installation, fix it by:
```bash
rm /usr/local/bin/bazel && ln -s $(which bazelisk) /usr/local/bin/bazel
```

If you're still having issues with the `bazel` command not being found, ensure your PATH is properly configured in your `.zshrc`:
```bash
# Add this line to your ~/.zshrc if it's not already there
export PATH=$HOME/bin:/usr/local/bin:$HOME/.local/bin:/opt/homebrew/bin:$PATH

# Then reload your shell configuration
source ~/.zshrc
```

## Setup Sections

(More sections will be added as configurations are implemented)

## License

This project is licensed under the MIT License - see the LICENSE file for details. 