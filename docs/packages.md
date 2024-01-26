# Frontend Installations

You’ll need to install Node.js + npm, React.js, and Prettier. It’s best to consult the documentation at their respective sites, https://nodejs.org/en/download, https://react.dev/learn/installation, and https://prettier.io/docs/en/install.html

_There may be issues installing Node.js from the default apt repository on Ubuntu. If there’s an error, follow this guide for Node.js installation from source:_

[How to Install ReactJS on Ubuntu Linux](https://www.linuxcapable.com/how-to-install-reactjs-on-ubuntu-linux/#Install-Nodejs-on-Ubuntu-2204-or-2004-For-Reactjs) and [NodeJS installation on Ubuntu](https://github.com/nodesource/distributions#installation-instructions)

# Backend Installations

You’ll need to install Anaconda, MongoDB (Community), and all of the dependencies specified in the codebase.

## Anaconda

To install Anaconda, consult the installation instructions in

[Automation Onboarding](https://www.notion.so/Automation-Onboarding-4fe446b52e134d0faac2126e72a949bc?pvs=21)

## MongoDB

Follow the instructions on the Mongo website to install according to your computational setup.

https://www.mongodb.com/docs/manual/administration/install-community/

## Dependencies

Since the application runs on Python, you can install the dependencies using Python’s package manager, pip.

```jsx
~/path-to-dir/hydro-directory$ pip install -r requirements.txt
```

Make sure you are in the right directory or this command will not work as intended!

# Firmware Installations

We do firmware development in PlatformIO. It can be installed into VSCode (recommended) by following the instructions on [this page](https://docs.platformio.org/en/latest/integration/ide/vscode.html#installation).

The IDE can also be directly installed with the [download page](https://platformio.org/install) if you prefer that and are working on Windows.
