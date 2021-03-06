# Tag Command Line Interface

*This tool is under active development! Breaking changes may be on the horizon. If you depend on `tagcli` for day to day use, please reach out to @bruab when stuff goes wrong.*

tagcli is a command line tool for locally hosting frontend snippets. You can use it to develop personalization campaigns and experiments for Optimizely Classic, Optimizely X, Adobe Test & Target, VWO, Google Optimize, and any similar platform.

It consists of a local server to host your code and a [Tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en) script to inject it.

### Dependencies

You'll need to have [node.js](http://nodejs.org/) installed locally to run `tagcli` and the Tampermonkey extension to view variations locally.

## Installation

⚠️ WIP post-fork - TODO this doesn't work yet :)

```
npm install -g tagcli
```

## Quickstart

- Create local JavaScript, CSS or HTML files to inject
- Create a .json file with the path to these files
- Execute the following command:

```
tagcli host <path/to/some.json>
```

- Visit https://localhost:8080 and follow the instructions to install the Tampermonkey userscript
- Append `?tagcli=activate` to any page on which you want to inject your code

## What goes in the .json file

At the minimum, your file must define an array of `"files"` to host. For a minimal example, see `demo/sample/minimal.json`. Hosting this file with `tagcli` will inject the contents of a single JavaScript file into the browser.

You can define as many files as you want, with ".js" or ".css" extensions. They'll be added to the page in the order listed.

Optionally, you can define an `"inject"` condition to ensure that your code only runs after a certain statement evaulates to `true`. TODO example

## Copyright and license

Code copyright 2015 Celerius Group Inc. Released under the [Apache 2.0 License](http://www.apache.org/licenses/LICENSE-2.0).
