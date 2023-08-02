# strapi-plugin-editorjs

<h1 align="center">Editorjs for Strapi</h1>

<p align="center">Replace Strapi WYSIWYG with Editorjs</p>


## 👋 Get Started
Features
Installation
Configuration
Contributing
Requirements

## ✨ Features
- [x] Paragraph Tool (default)
- [x] [Embed Tool](https://github.com/editor-js/embed)
- [x] [Table tool](https://github.com/editor-js/table)
- [x] [List Tool](https://github.com/editor-js/list)
- [x] [Warning Tool](https://github.com/editor-js/warning)
- [x] [Code Tool](https://github.com/editor-js/code)
- [x] [Link Tool](https://github.com/editor-js/link)
- [x] [Image Tool](https://github.com/editor-js/image)
- [x] [Raw HTML Tool](https://github.com/editor-js/raw)
- [x] [Heading Tool](https://github.com/editor-js/header)
- [x] [Quote Tool](https://github.com/editor-js/quote)
- [x] [Marker Tool](https://github.com/editor-js/marker)
- [x] [Checklist Tool](https://github.com/editor-js/checklist)
- [x] [Delimiter Tool](https://github.com/editor-js/delimiter)
- [x] [InlineCode Tool](https://github.com/editor-js/inline-code)

## 🔧 Installation
```bash
yarn add strapi-plugin-react-editorjs
# or
npm install strapi-plugin-react-editorjs
```

In order for Strapi to show the Link Tool thumbnails correctly, you will need to edit the 'strapi::security' line in ./config/middlewares.js. Change that line to the following (do this at your own risk).

```js
module.exports = [
  // ...
  {
    name: 'strapi::security',
    config: {
      contentSecurityPolicy: {
        directives: {
          'img-src': ['*'],
        },
      }
    },
  },
  // ...
];
```


## 🤟🏻 Getting Started

```bash
yarn add strapi-plugin-react-editorjs
# or
npm install strapi-plugin-react-editorjs
```

In order for Strapi to show the Link Tool thumbnails correctly, you will need to edit the 'strapi::security' line in ./config/middlewares.js. Change that line to the following (do this at your own risk).

```js
module.exports = [
  // ...
  {
    name: 'strapi::security',
    config: {
      contentSecurityPolicy: {
        directives: {
          'img-src': ['*'],
        },
      }
    },
  },
  // ...
];
```

In ./config/plugins.js add the following :

```js
export default ({ env }) => ({
  // ...
  "editorjs": {
    enabled: true,
  },
  // ...
})
```


## ⚙️ How to extend/develop this plugin (optional)

If you want to change the look of the editor or add/remove editorJS plugins, you will need to do the following:

1. If this plugin is already install via yarn or npm, uninstall:
```bash
yarn remove strapi-plugin-react-editorjs
# or
npm uninstall strapi-plugin-react-editorjs
```
2. Go to the ./src/plugins folder (create it if it doesn't exist) and clone the project:

```bash
# If you wish to clone the Master Branch
git clone https://github.com/melishev/strapi-plugin-react-editorjs.git
# If you wish to clone the Beta Branch
git clone --single-branch --branch beta https://github.com/melishev/strapi-plugin-react-editorjs.git
```
3. Go into the plugin and install dependencies:
  - `cd strapi-plugin-react-editorjs`
  - `yarn install` or `npm install`
4. In an editor add the following code into the main Strapi v4 ./config/plugins.js file (create the file if it doesn't exist)

```js
module.exports = ({ env }) => ({
  // ...
  'editorjs': {
    enabled: true,
    resolve: './src/plugins/strapi-plugin-react-editorjs'
  },
  // ...
})
```

5. To make changes to EditorJS plugins, edit the `./src/plugins/strapi-plugin-react-editorjs/admin/src/config/customTools.js` file.
  - Note: the Image Tool add-on has been highly customized in order to work in Strapi and cannot be edited in the `customTools.js` file. If you wish to develop it further, you may, but it will take much more advanced knowledge and testing.
6. Rebuild Strapi after installation and after any changes made in the plugin.
```bash
yarn build
# or
npm run build
```

### Please note that the add-ons are configured for Strapi, be careful when changing the configuration.

<br>

#### Forked from https://github.com/melishev/strapi-plugin-react-editorjs
