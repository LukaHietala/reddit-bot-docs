---
description: >-
  Before getting the bot to work, let's start off by checking some things from
  your list
---

# Prerequisites

## Requirements

* [ ] Python, version 3.9+.

### Python

First of all, check if you have Python 3.9+ already installed by running `python3 --version` (if this does not work, try `python --version`).

It returns the following output:

```pwsh
Python 3.9.0
```

Or anything above, than you can go to the next step.

If it returns the following output:

```pwsh
python3: command not found
```

Then you need to install Python.

#### Installing python on windows

The easiest way to install Python on Windows is to use the [Python for Windows installer](https://www.python.org/downloads/windows/).

When you install Python this way, you will see a checkbox at the bottom which says _Add Python 3.10.x to PATH._ **Make sure you check this box, it is extremely crucial!**

![ipfw](<.gitbook/assets/image (2) (1).png>) ![ipfw](<.gitbook/assets/image (4).png>)

Alternatively, you can download python from the Microsoft Store (do not recommend, it's an outdated version and not supported by the official developers).

Finally, you can download python using a Package Manager (e.g. [Chocolatey](https://chocolatey.org/)) by running the following command:

```pwsh
choco install python
```

#### Installing python on MacOS

The easiest way to install Python 3.9+ on MacOS is to use the [Installer for Python](https://www.python.org/downloads/mac-osx/).

Once you landed on the download page, click on Latest Python3 release. Then, go to the end of the page and click the `macOS 64-bit universal2 installer` button.

Then, click the `Install` button until the installation is complete.

Then, to check if everything is working, run the following command:

```bash
python3 --version
```

If it returns the following output:

```bash
Python 3.9.0
```

Or anything above, than you can go to the next step.

You can also install Python on MacOS by using the [Homebrew](https://brew.sh/) package manager.

After installing Homebrew, run the following command:

```bash
brew install python@3.9
```

(I do recommend you install the latest version of python

```bash
brew install python@3.10
```

)

#### Installing python on Linux

Python may be installed on your system by default. Check it using the following command:

```bash
python3 --version
```

If it returns the following output:

```bash
Python 3.9.0
```

Or anything higher, then you are good to go!

Python can be installed by using your package manager (e.g. [apt-get](https://www.debian.org/), [yum](https://www.yum.com/), [pacman](https://www.archlinux.org/), [zypper](https://www.opensuse.org/) etc.).

Voila! You are done. 👍
