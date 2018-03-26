<p align="left">
  <a href="https://www.amie-chen.com/pretzel/" target="_blank">
    <img alt="Parcel" src="./screenshot/logo.png" width="200">
  </a>
</p>
###### This repository of Pretzel and any affiliated releases are edits by me, Rick Sheahan, on the initial MIT Licensed codebase by Amie Chen, who created the program and deserves the recognition. In addition to my code changes, I have edited the download link, the show/unshow hotkey that is listed, and the running it locally section of this readme. Please refer to the original repo at [https://github.com/amiechen/pretzel](https://github.com/amiechen/pretzel) to get the original,

Pretzel is Mac desktop app that shows and search keyboard shortcuts based on your current app. [Checkout the lading page here.](https://www.amie-chen.com/pretzel)

## Features

* 🔍 In-App quick search: Find your specific shortcut with quick search among hundreds.
* ⚡ Detects the currently focused app.
* 🐠 Little distraction from your current task. Clicking on the menubar icon or simultaneously pressing the keys of the hotkey `⌘+⌥+⇧+P` will automatically opens the shortcut panel.

![app-screen-shot](./screenshot/app-screen.png)

## Download for Mac

[Download the latest <rick-fork> release](https://ricksheahan.io/downloads/Pretzel.app)

## Run it locally (if you are curious):

```
npm install
npm start
```

To compile:

```
npm run build:mac
npm run build:win
```

### Building from source on a Mac for macOS
The above reccomendation has a high potential to cause problems with attemopts to build or run pretzel from cloning the git directory and using npm/Node like normal. Instead, the most deterministic and problem-free method that is currently known is to get rid of existing Node installations along with any version managers or npm-related files. This is especially importat (and easy) if you have installed node via Homebrew. 
The process is essentially install Homebrew, install nvm from online source using curl or wget (which you can install with Homebrew!), install the `lts/carbon` alias of Node in addition to whatever other versions you want, and make sure nvm is using it. Then use Homebrew to install yarn (minus Node, since you have nvm). What is a potential source of frustration is not knowing that you need `electron-packager` installed via yarn, which is usually done globally. From there, the process is similar, just with `yarn` instead of `npm`. Then you should be able to build with `yarn run:build mac` and have very few problems.

#### Step by Step Instructions
1. **Uninstall Node**, npm, nvm, n, or any other utilities that are along the same lines. This will be temporary - if you make a note of your globally installed packages in `usr/bin/node_modules` and the versions you are using with `npm -v` and `node -v`, you should have no problem getting your previous setup back - improved, with way less headaches! If you installed with Homebrew, sorry, but Node is one thing that shouldn't be left to the tipsy package manager. For Homebrew, its `brew uninstall Node`, otherwise you need to look at the documentation of the source of your Node installation.
2. **Install [Homebrew](https://brew.sh)** if you don't already have it. If you haven't used it, you are likely new to macOS dev environments - so get used to seeing it alot! Often just called brew, and indeed called in the terminal with `brew`, it's the most widely used and generally appreciated package manager that picks up Apple's slack. You can technically do this after the last step, but if you run `brew install wget` after you have Homebrew installed, then you can use *either* of the two ways `nvm` reccomends that you download it.
3. **Install [nvm](https://github.com/creationix/nvm#install-script)** from source in your terminal by using either of the two methods reccomended on their website. If you didn't get wget earlier, just go with cURL - you should have it by default: `curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash` . Reopen your terminal client and run `command -v nvm` to make sure it is installed and pathed correctly; it should output `nvm`.
4. Install [Yarn](https://yarnpkg.com/lang/en/docs/install/) via Homebrew, with a caveat. Yarn automatically installs Node when you install it with Homebrew, so you have to install it with a special flag to make sure it won't mess up your nvm setup: `brew install yarn --without-node
`Yarn is sort of intended to be a better designed `npm` that still is mostly "backwards compatible" with npm. While using Yarn, you generally get more deterministic results and minimize frustrating errors due to differences in environments of the repo owner's software setup and yours. Bear in mind that you need to start checking in `yarn.lock` when you commit to repos.
5. Clone the repo using your terminal in a directory of your choice, either from the original repo `git clone https://github.com/amiechen/pretzel` or my fork with `https://github.com/cucumbur/pretzel` (my "fixed" / forked version for fixing issues and adding features and contributing any wanted changes back to the original repo if asked).
6. Here's a biggie the docs and myself overlooked - you need `electron-packager` installed globally for anything to work, but it is not listed in any of the dependencies. So, install it globally using yarn like so: `yarn global add electron-packager`
7. Navigate your terminal into the pretzel directory and simply run `yarn` to install all the modules and other work that `npm install` does - with much less complication and generally way faster.
8. With your terminal in the pretzel base directory, execute `yarn run build:mac` and your release will start to be built, with realtime updates you can watch. It will show up in a new subdirectory of pretzel. 

An thats it! You should have a fully working, customizable version of pretzel!


## Add a shortcut:

1.  Fork the repo on github. If you don't have a github account, feel free to do send me the `.yml` file once you finish step 2 and 3.
2.  Create a text file with <your-app-name>.yml as the file name. For example, `Photoshop.yml`.
3.  Find your app's shortcuts on the web and add them to your `.yml` file, in the same format as the files in `/shortcuts` folder.
4.  Make a PR and I will merge it in and let you know.
5.  Once it's released, if you already have pretzel installed the app will notify you to install an update. If not, download [the Pretzel page]() for the latest release.

## License

MIT © [Amie Chen](https://amie-chen.com)

Contributions by Rick Sheahan, who is still reading up on licensing.
