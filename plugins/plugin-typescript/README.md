# @snowpack/plugin-typescript

This plugin adds TypeScript type checking to any Snowpack project.

When developing or building your site with Snowpack, this plugin will run TypeScript's `tsc` CLI in your project and pipe the output through Snowpack. Works with all version of TypeScript, as long as TypeScript is installed separately in your project.

## Usage

```bash
npm i @snowpack/plugin-typescript typescript
```

Then add the plugin to your Snowpack config:

```js
// snowpack.config.js

module.exports = {
  plugins: ['@snowpack/plugin-typescript'],
};
```

### Usage with Typescript transformers

If you need to use some TypeScript transformer, you will have to install the `ttypescript` too, and configure the plugin with `allowTransformers`.

```bash
npm i ttypescript
```

And your `snowpack.config.js` should be like:

```js
// snowpack.config.js

module.exports = {
  plugins: [
    ['@snowpack/plugin-typescript', { allowTransformers: true }]
  ],
};
```

## Plugin Options

| Name   |   Type   | Description                                                                                                                                                                               |
| :----- | :------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `args` | `string` | Optional arguments to pass to the `tsc` CLI. For example, you can configure a custom project directory (with a custom `tsconfig.json` file) using `args: "--project ./your/custom/path"`. |
| `allowTransformers` | `boolean` | Optional argument. When `true`, it will call the `ttsc` instead of the `tsc`, which will allow you to configure and use transformers defined in you `tsconfig.json` file. |
