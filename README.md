# (REMAKE) APlayer - a lovely HTML5 music player

![GitHub package.json version](https://img.shields.io/github/package-json/v/LittleYe233/APlayer?style=flat-square)

**Original Repository:** [DIYgod/APlayer](https://github.com/DIYgod/APlayer)

**Visit the original repository for further information. Here are only differences from that.**

## Install

### NPM

Note that the name of this package is "aplayer-remake".

## Changed APIs

### `ap.list.add(audios, index = null)`

**Parameters**:

-   `audios`: audio or list of audios
-   `index`: position to be added

## Development

### Install dependencies

APlayer depends on [node-sass](https://github.com/sass/node-sass), which needs node-gyp to compile. So the compilation environment should be prepared well.

This [issue](https://github.com/nodejs/node/issues/38367) mentions some combinations of basic factors (e.g. Node version, C++ compilation flags). One possible environment is:

-   Node version: v16.15.1
-   yarn version: v1.22.19
-   C++ compilation flags: `--std=c++14`

So to install the dependencies, first install gcc and make, which are probably already stored in package repositories of your distro (follow the instructions for your current distro). Then clone the repo and change directory into it:

```bash
git clone https://github.com/LittleYe233/APlayer.git
cd APlayer
```

Make sure yarn is installed:

```bash
npm install -g yarn
```

After that install all the dependencies with appropriate compilation flags:

```bash
CXXFLAGS="--std=c++14" yarn
```

Now the repo is ready for development and test.

## Demo

The scripts and code of demo are almost located in `demo/` subfolder. You can execute `npm run start` in terminal to launch the demo.

Note that it won't open in browser by default. To change this behavior, edit `webpack/dev.config.js` and find `devServer` field:

```js
devServer: {
    compress: true,
    contentBase: path.resolve(__dirname, '..', 'demo'),
    clientLogLevel: 'none',
    quiet: false,
    open: false,
    historyApiFallback: {
        disableDotRule: true,
    },
    watchOptions: {
        ignored: /node_modules/,
    },
},
```

Change the value of `open` to `true`.

In the original repo, most resource links can't be reached for restriction (will return 403 error). You can download essential assets from [here](https://github.com/LittleYe233/APlayer/releases/tag/demo_assets-1.1.0).

## Major updates

-   Add more descriptions on development guide and demo.
-   Replace unreachable links.
-   Expand panel of fixed player to full width of the current webpage.
-   Allow to add songs at any index of playlist.
-   Some APIs are added, removed and changed.
