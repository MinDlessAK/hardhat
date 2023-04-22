# Sample Hardhat Project

This project demonstrates a basic Hardhat use case. It comes with a sample contract, a test for that contract, and a script that deploys that contract.

#3. Creating a new Hardhat project
We'll install Hardhat using the Node.js package manager (npm), which is both a package manager and an online repository for JavaScript code.

You can use other package managers with Node.js, but we suggest you use npm 7 or higher to follow this guide. You should already have it if you followed the previous section's steps.

Open a new terminal and run these commands to create a new folder:
```shell
mkdir hardhat-tutorial
cd hardhat-tutorial
```
Then initialize an npm project as shown below. You'll be prompted to answer some questions.

TIP

Use the tabs in the snippets to select your preferred package manager. We recommend using npm 7 or later, since it makes installing Hardhat's dependencies much easier.

```shell
npm init
```
Now we can install Hardhat:
```shell
npm install --save-dev hardhat
```
In the same directory where you installed Hardhat run:
```shell
npx hardhat
```
Select Create an empty hardhat.config.js with your keyboard and hit enter.
```shell

$ npx hardhat
888    888                      888 888               888
888    888                      888 888               888
888    888                      888 888               888
8888888888  8888b.  888d888 .d88888 88888b.   8888b.  888888
888    888     "88b 888P"  d88" 888 888 "88b     "88b 888
888    888 .d888888 888    888  888 888  888 .d888888 888
888    888 888  888 888    Y88b 888 888  888 888  888 Y88b.
888    888 "Y888888 888     "Y88888 888  888 "Y888888  "Y888

👷 Welcome to Hardhat v2.9.9 👷‍

? What do you want to do? …
  Create a JavaScript project
  Create a TypeScript project
❯ Create an empty hardhat.config.js
  Quit
```
When Hardhat is run, it searches for the closest hardhat.config.js file starting from the current working directory. This file normally lives in the root of your project and an empty hardhat.config.js is enough for Hardhat to work. The entirety of your setup is contained in this file.

# Hardhat's architecture
Hardhat is designed around the concepts of tasks and plugins. The bulk of Hardhat's functionality comes from plugins, and you're free to choose the ones you want to use.

#Tasks
Every time you're running Hardhat from the command-line, you're running a task. For example, npx hardhat compile is running the compile task. To see the currently available tasks in your project, run npx hardhat. Feel free to explore any task by running npx hardhat help [task].

#Plugins
Hardhat is unopinionated in terms of what tools you end up using, but it does come with some built-in defaults. All of which can be overridden. Most of the time the way to use a given tool is by consuming a plugin that integrates it into Hardhat.

In this tutorial we are going to use our recommended plugin, 
@nomicfoundation/hardhat-toolbox
, which has everything you need for developing smart contracts.

To install it, run this in your project directory:
```shell
npm install --save-dev @nomicfoundation/hardhat-toolbox
```
Add the highlighted line to your hardhat.config.js so that it looks like this:
```shell
require("@nomicfoundation/hardhat-toolbox");

/** @type import('hardhat/config').HardhatUserConfig */
module.exports = {
  solidity: "0.8.18",
};
```


Try running some of the following tasks:

```shell
npx hardhat help
npx hardhat test
REPORT_GAS=true npx hardhat test
npx hardhat node
npx hardhat run scripts/deploy.ts
```
