# yogi alloy

![Pixel Alloy](http://cl.ly/image/110y3s2w2n1l/yogi.jpg)

This project provides common [AlloyUI](http://alloyui.com) tasks for [yogi](http://yui.github.com/yogi) command line tool.

## Usage

	ya [command] [--flags]

## Dependencies

In order to sucessfully run all yogi alloy commands you must have the following dependencies installed:

1. [Node.js](http://nodejs.org/download/)
2. [Compass](http://compass-style.org/install/)

## Install

	npm -g install yogi yogi-alloy yuidocjs docpad shifter

## Available commands

```
ya help
```

### AlloyUI

Provides a set of util commands to work with [AlloyUI](http://github.com/liferay/alloy-ui) project.

* Clone or update all dependencies. Also incorporate `ya build` task.

	```
ya init
	```

* Build components guessing what do build.

	```
ya build [--js, --css, --fast]
	```

	If you run this command inside of a component folder, e.g. `src/aui-audio`, it will build only that component on `build/aui-audio`. If you run this command inside of the root folder it will build all components on `build` folder.

* Create a new module. For example:

    ```
ya create --name foo
    ```

	This will generate a `src/aui-foo` folder containing the module scaffolding.

* Release a new version.

	```
ya release
	```

	This will generate a ready-to-release version of AlloyUI inside of a .zip file.

### Alloy Twitter Bootstrap

Provides a set of util commands to work with [Alloy Twitter Bootstrap](http://github.com/liferay/alloy-twitter-bootstrap) project.

* Compile SASS files to CSS.

	```
ya css-compile
	```

* Watch changes on SASS files and build them.

	```
ya css-watch
	```

* Finds all CSS files in the current directory and namespace them. For example:

    ```
ya css-namespace --prefix foo
    ```

    Turns `.bar {}` into `.foo-bar {}`.

### AlloyUI.com

Provides a set of util commands to work with [AlloyUI.com](http://github.com/liferay/alloyui.com) project.

* Run the website locally and watch for any changes.

	```
ya site-watch
	```

* Deploy the website to alloyui.com.

	```
ya site-deploy
	```

	In order to see your changes live at http://alloyui.com you'll need a git remote pointing to liferay's repository. You can do that by running `git remote add upstream git@github.com:liferay/alloyui.com.git`. Then, when you get asked about what remote do you want to deploy, just answer `upstream`.

### API Docs

Provides a set of util commands to work with AlloyUI's [API Docs](http://alloyui.com/api/).

* Run the API Docs locally and watch for any changes.

	```
ya api-watch
	```
	Go to `http://localhost:3000` to see it.

* Build the API Docs locally.

	```
ya api-build
	```
	This command will scan all JavaScript files inside of your current folder to generate a documentation on `api` folder. You can also set a specific source/destination folder by answering command's questions.

## Contributing

Contribute new tasks to yogi alloy is really easy:

1. [Install yogi alloy](#install) and its [dependencies](#dependencies), if you haven't done it yet.
2. Fork and clone [yogi alloy](http://github.com/liferay/yogi-alloy).
3. Replace it with your cloned version, to do that follow the next steps:

	a) Move the old symbolic link form your way:

	```
mv /usr/local/bin/yogi-alloy /usr/local/bin/yogi-alloy-npm
	```

	b) Create a symbolic link for your cloned version.

	```
ln -s /Users/you/yogi-alloy/bin/yogi-alloy.js /usr/local/bin/yogi-alloy
	```
	> **Note:** Remember to change "you" to your own username.

4. In your clone, copy the contents of the `hello` command to `my-command`:

	```
cp -R lib/cmds/hello.js lib/cmds/my-command.js
	```

5. Start working on it and when you finish, just send a pull request with your new command.
6. If the pull gets approved, it will be available in the next version under [npm](https://npmjs.org/package/yogi-alloy).
7. Run your command:

	```
ya my-command
	```

> **Note:** These instructions works on unix-based systems. If you're on Windows, [check instructions here](https://github.com/liferay/yogi-alloy/wiki/Contributing-(Windows)).