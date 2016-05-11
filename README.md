# Bi Sheng

> [Bi Sheng](https://en.wikipedia.org/wiki/Bi_Sheng) was the Chinese inventor of the first known movable type technology.

`bisheng` is designed to transform [Markdown](https://en.wikipedia.org/wiki/Markdown) into static websites and blogs using [React](https://facebook.github.io/react/).

## Usage

### Use `bisheng` in a new project

```bash
git clone git@github.com:benjycui/bisheng-theme-one.git myblog && cd myblog
rm -rf .git && npm i && npm start
open http://127.0.0.1:8000/
```

### Use `bisheng` in current project

Installation:

```bash
npm install --save-dev bisheng
```

Then, add `start` to [npm scripts](https://docs.npmjs.com/misc/scripts):

```json
{
  "scripts": {
    "start": "bisheng start"
  }
}
```

Create `bisheng.config.js`, otherwise `bisheng` will use the default config:

```js
module.exports = {
  source: './posts',
  output: './_site',
  theme: './_theme',
  port: 8000,
};
```

**Note:** please make sure that `source` and `theme` exists, and `theme` should not be an empty directory. Just copy [bisheng-theme-one](https://github.com/benjycui/bisheng-theme-one) to `theme`, if you don't konw how to develop a theme.

Now, just run `npm start`.

## Documentation

### CLI

We can install `bisheng` as a cli command and explore what it can do by `bisheng -g`. However, the recommanded way to use `bisheng` is that install it as `devDependencies`.

```bash
npm install -g bisheng
bisheng -h
```

### Configuration

`bisheng` will read `bisheng.config.js` as its config file, but we can set the config file name by `--config`, something like this `bisheng --config another.config.js`.

The content of `bisheng.config.js` looks like this:

```js
module.exports = {
  source: './posts',
  output: './_site',
  theme: './_theme',
  port: 8000,
  root: '/',
  plugins: [],
};
```

#### source: String|Array[String]

To set directory/directories where we place markdown files.

#### output: String

To set directory where `bisheng` will generate (HTML & CSS & JavaScript) files to.

#### theme: String

To set directory where we put the theme of website.

#### port: Number

To set the port which will be used when start a local server.

#### root: String

If the website will be deploy under a sub-directory of a domain(something like `http://benjycui.github.io/bisheng-theme-one/`), we must set it(such as `/bisheng-theme-one/`).

#### plugins

// TBD

### How to develop a theme

// TBD

### How to develop a plugin

// TBD

## Liscense

MIT
