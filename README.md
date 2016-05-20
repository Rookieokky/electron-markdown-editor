# Electron markdown editor

## Screenshot

![Screenshot](resources/electron-markdown.png)

[<img src="https://cdn.rawgit.com/diversen/electron-markdown-editor/master/assets/electron-logo.svg" align="right" width="200">](http://electron.atom.io)

A markdown editor for the desktop using:

* [Electron](http://electron.atom.io/)
* The CSS frammework [Uikit](http://getuikit.com/) 
* The Uikit [HTML-editor](http://getuikit.com/docs/htmleditor.html)

## Features

* WYSIWYG
* Dialog for image
* Dialog for videos (mp4)
* Dialog for tables
* Live preview of code [highlight.js](https://highlightjs.org/) with `tiles` ~~~ code ~~~

* Live preview of Math [MathJax](https://www.mathjax.org/), e.g.:

$$\sum_{i=0}^n i^2 = \frac{(n^2+n)(2n+1)}{6}$$

* The parsing of markdown is done with [markdown-it](https://github.com/markdown-it/markdown-it) 

## Install

Use npm:

Global: 

    sudo npm install electron-markdown-editor -g
    
You can specify one file on the commandline. E.g.: 
    
    electron-markdown-editor README.md

## Development: 
	   
    sudo npm install electron-prebuilt -g
    git clone https://github.com/diversen/electron-markdown-editor
    cd electron-markdown-editor 
    npm install
    ./bin/electron-markdown-editor README.md
    
or (this option does not calculate added file from commandline correct) 

    electron app.js 


## Build

Build for win32. (highly experimental)

    ./win-build.sh

Build for osX (highly experimental)

Run:

	./osx-build.sh

The final installer file is quite large as the system uses mathjax which takes up about 20MB or so. It will take a good amount of time. 30 minutes or so. (On a quite old computer). 

## Notes

About creating a npm bin file, when doing `npm install electron-markdown-editor -g`. 

http://blog.soulserv.net/building-a-package-featuring-electron-as-a-stand-alone-application/


## Obsolete

Notes: 

The next section is obsolete as the `electron-markdown-editor` now uses `dist` packages for packages. This is because it easier to just use this, when there is dist versions of all packages. It is also easier to move right to the web. 

Building of the `scripts/bundle.js` is done with `browserify` and `watchify`

    watchify scripts/md.js -o scripts/bundle.js

Or: 

    watchify scripts/md.js -o 'uglifyjs -cm > scripts/bundle.js'

