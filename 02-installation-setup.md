# Installation and Setup

This guide will walk you through installing Git and setting up your GitHub account.

## Installing Git

### Windows

1. Download the installer from the [official Git website](https://git-scm.com/download/win)
2. Run the installer and follow the installation wizard
3. During installation, you can keep most default settings, but consider these options:
   - Choose "Git from the command line and also from 3rd-party software"
   - Choose "Use the OpenSSL library" for HTTPS connections
   - Choose "Checkout Windows-style, commit Unix-style line endings"
   - Choose "Use Windows' default console window"
   - Enable "Git Credential Manager"

### macOS

#### Using Homebrew (recommended)
```
brew install git
```

#### Using the installer
1. Download the installer from the [official Git website](https://git-scm.com/download/mac)
2. Run the installer and follow the installation wizard

### Linux (Debian/Ubuntu)
```
sudo apt update
sudo apt install git
```

### Linux (Fedora)
```
sudo dnf install git
```

## Verifying Installation

To verify Git is installed correctly, open a terminal or command prompt and run:
```
git --version
```

You should see output displaying the installed Git version.

## Initial Git Configuration

After installing Git, set up your identity with these commands:

```
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Optional but recommended configurations:

```
# Set default editor (replace with your preferred editor)
git config --global core.editor "code --wait"  # For VS Code

# Set default branch name to main
git config --global init.defaultBranch main

# Enable colorful output
git config --global color.ui auto
```

## Setting Up GitHub Account

1. Go to [GitHub's signup page](https://github.com/join)
2. Enter your username, email address, and password
3. Verify your email address
4. Optionally complete your profile with a picture and additional information

## Connecting Git to GitHub

### Using HTTPS (Simplest method)

When pushing to GitHub for the first time, you'll be prompted to enter your GitHub username and password.

For increased security with HTTPS, it's recommended to use a personal access token instead of your password:

1. Go to GitHub → Settings → Developer settings → Personal access tokens
2. Click "Generate new token"
3. Select the appropriate scopes (at minimum, select "repo")
4. Generate the token and save it somewhere secure

### Using SSH (Recommended for frequent use)

1. Generate an SSH key pair:
   ```
   ssh-keygen -t ed25519 -C "your.email@example.com"
   ```

2. Start the SSH agent:
   ```
   # For Windows
   eval "$(ssh-agent -s)"
   
   # For macOS/Linux
   eval "$(ssh-agent -s)"
   ```

3. Add your SSH key to the agent:
   ```
   ssh-add ~/.ssh/id_ed25519
   ```

4. Copy your public key:
   ```
   # For Windows
   cat ~/.ssh/id_ed25519.pub | clip
   
   # For macOS
   pbcopy < ~/.ssh/id_ed25519.pub
   
   # For Linux
   xclip -sel clip < ~/.ssh/id_ed25519.pub
   # or
   cat ~/.ssh/id_ed25519.pub
   # Then manually copy the output
   ```

5. Go to GitHub → Settings → SSH and GPG keys → New SSH key
6. Paste your public key and save

## Next Steps

Now that you have Git installed and your GitHub account set up, you can proceed to learn about [Basic Git Commands](03-basic-commands.md). 