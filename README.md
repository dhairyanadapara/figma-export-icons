# figma-export-icons-2

<a href="https://www.npmjs.com/package/figma-export-icons-2"><img src="https://badgen.net/npm/v/figma-export-icons-2" alt="Version"></a>
<a href="https://www.npmjs.com/package/figma-export-icons-2"><img src="https://badgen.net/npm/dm/figma-export-icons-2" alt="Downloads"></a>

> Command line script to export and download icons from a Figma file using the Figma REST api.

> This cli application is extended version of [figma-export-icons](https://github.com/tsimenis/figma-export-icons). I have made few changes to download the icons in multiple format.

## Description

Running the script will bring up a wizard to fill in the config for fetching the assets. You can also provide the icons-config.json yourself, then the wizard is skipped.
After the config is provided, the figma file is fetched and parsed to find the icons frame, the files are downloaded and put locally in the directory provided in the config.

example config file:

```json
{
    "figmaPersonalToken": "YOUR_PERSONAL_TOKEN",
    "fileId": "FILE_ID",
    "page": "Identity",
    "frame": "Icons",
    "iconsPath": "assets/svg/icons",
    "format": "svg",
    "scale": 4
}
```

## Features

-   Wizard to generate config, you will be prompted for any missing key
-   icons-config.json is automatically added to .gitignore if it exists
-   Directory to save the icons is created if it doesn't exist
-   Icons are deleted from local directory when fetching new
-   Icons with the same name are marked with `${iconName}-duplicate-name.svg` so you can easily spot them and fix figma file
-   Running the script with `-c` will clear the config and run the wizard again
-   You can use a custom path to your configuration file with `--config=path/to/config.json`
-   You can pass the output format of image. It supports jpg, png, svg, and pdf.
-   For png, jpg and pdf it supports scale property.

## Installation

Install the cli globally so you can use it on any directory

```sh
npm install -g figma-export-icons
```

Or if you prefer install it in your project

```sh
npm install figma-export-icons --save
```

## Usage

If you have installed the module globally:

```sh
export-icons
```

If you have installed it locally:

Create a script in your package.json

```js
scripts: {
 'export-icons': 'export-icons'
}
```

and run

```sh
npm run export-icons
```

OR

run it directly with:

```sh
npx export-icons
```

For running it as a cli app:

1. clone the app or download zip from [repo](https://github.com/dhairyanadapara/figma-export-icons)
2. run cli.js:

```sh
node cli.js
```

## Credits

This script was developed and is part of our tools at [Zuru Tech](https://zuru.tech/).
