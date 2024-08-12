---
title: Pre-Requisites
nav: true
---

# Workshop Pre-Requisites

To run this workshop, you will need to have the following:

1. Have a [GitHub](https://github.com) account.
2. Install [Podman](https://podman.io/docs/installation).
3. Install [Python](https://git-scm.com/)


## Install Git

If you do not have a GitHub account, you can create by visting: [https://github.com/](https://github.com/) and signup.

**Mac Users**
  
You can install `git` for Mac by running:

```brew install git ```

**Note**: In case if you do not have brew installed: visit: [https://brew.sh/](https://brew.sh/) 

**Debian/Ubuntu Users**

`sudo apt-get install -y git`

**Fedora/RHEL/CentOS Users**

`sudo dnf install -y git`

**Windows Users**

You can isntall git by running:

`winget install --id Git.Git -e --source winget`

Alternatively, you can download and install Git from the official website: [https://git-scm.com/download/win](https://git-scm.com/download/win)

**Configure Git**:

**Set your username**

`git config --global user.name "Your Name"`

**Set your email**

`git config --global user.email "your.email@example.com"`

## Install Python

**Mac Users**

You can install python by running:

`brew install python`

**Linux Users**

**For Debian/Ubuntu**

`sudo apt-get install -y python3 python3-pip`

**For Fedora/RHEL/CentOS**

`sudo dnf install -y python3 python3-pip`

**Windows Users**

1. Download Python from: [https://www.python.org/downloads/](https://www.python.org/downloads/)
2. Run the installer and ensure you check "Add Python to PATH" during the installation.


## Install Podman

**For Mac Users**

Install and start Podman machine:

`brew install podman`

Once its installed, try running:

`podman machine init`

`podman machine start`

**Linux Users**

**For Debian/Ubuntu**

`sudo apt-get update`

`sudo apt-get install -y podman`

Once its installed, try running:

`podman machine init`

`podman machine start`

**For Fedora/RHEL/CentOS**

`sudo dnf install -y podman`

Once its installed, try running:

`podman machine init`

`podman machine start`

**For Windows**

Please follow the steps listed here: [https://github.com/containers/podman/blob/main/docs/tutorials/podman-for-windows.md](https://github.com/containers/podman/blob/main/docs/tutorials/podman-for-windows.md)

Once its installed, try running:

`podman machine init`

`podman machine start`


