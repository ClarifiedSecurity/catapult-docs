# Getting started

Catapult can run in `Linux`, `Windows (WSL)` or `MacOS`. Recommended host OS is Ubuntu 22.04 LTS.

## Linux (Ubuntu/Debian)

- Make sure you have `git` & `make` installed:

  ```sh
  sudo apt update && \
  sudo apt install git make -y
  ```

- GOTO [Universal getting started](https://github.com/ClarifiedSecurity/Catapult#universal-getting-started)

## Windows WSL

You can run Catapult in WSL on Windows 10/11 but if you are unfamiliar with WSL and it's nuances then it might be easier to install Ubuntu 22.04 LTS on a VM and use that as your host OS. If you want to use WSL then follow the instructions below

From an admin PowerShell run:

- Install WSL & Ubuntu 22.04 LTS with:

```powershell
wsl --install
```

- Restart Windows, after restart Ubuntu setup should automatically run the, if not run Ubuntu it manually from the start menu and finalize the setup.
- Make sure you have `git` & `make` installed:

  ```sh
  sudo apt update && \
  sudo apt install git make keychain -y
  ```

- Make sure all of the SSH keypairs you need are in `~/.ssh` folder in the WSL Ubuntu and ssh-agent is started. For easy-to-use SSH Agent you can follow this [guide](https://esc.sh/blog/ssh-agent-windows10-wsl2/). You can use this method to add multiple keys to the SSH Agent.
- GOTO [Universal getting started](https://github.com/ClarifiedSecurity/Catapult#universal-getting-started)

**On Windows we suggest using [VSCode](https://code.visualstudio.com/) with the [Remote - WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl) extension to edit the files in WSL and [Windows Terminal](https://learn.microsoft.com/en-us/windows/terminal/install) for connection to the WSL.**

## MacOS

- Make sure you have brew and make installed:

  ```sh
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  brew install make
  ```

## Universal getting started

- Make sure you have a working [KeePass](https://keepassxc.org/) database with a key file. Catapult will not work without the KeePass key file so make sure your database is configured to use one.
- Make sure all of the SSH keypairs you need are loaded ssh-agent, because Catapult will use them to connect to the VMs.
- Clone the project from GitHub with:

  ```sh
  git clone https://github.com/ClarifiedSecurity/Catapult
  cd Catapult
  ```

- Create your own variables file based on the example:

  ```sh
  cp .makerc-vars.example .makerc-vars
  ```

- Fill out all of the required vars in `.makerc-vars`, To avoid any syntax errors don't leave a space after the `:=`, follow the instructions in the comments for each variable. All of the `KEEPASS_*` paths are case sensitive.
- Install all of the required dependencies for your host with:

  ```sh
  make prepare
  ```

- Start the Catapult container and connect to it with:

  ```sh
  make start
  ```

- Connect to an already started Catapult container with:

  ```sh
  make shell
  ```
