## Instructions to create this app from scratch

**Initial Project Setup**

- Create new directory && cd into directory
- `git init`
- `touch .tool-versions` and write `nodejs 14.16.1` in it _specifies the node version_
- `yarn init` _creates the package.json file_

**React App Setup**

- `touch index.js` _to create the initial React app_
  - write hello world app and use reactDOM to render it
- `yarn add react react-dom` _download and install react and react-dom. Don't forget to add node_modules to .gitignore_

**Bundle project together**

- Need webpack to bundle JS modules together to send to browser
  - `yarn add webpack webpack-cli` _cli is the tool to run webpack on the command line_
  - `touch webpack.config.js` _configure webpack. Set mode to development_

**Install Babel to allow webpack to read React**

- `yarn add babel-loader @babel/core @babel/preset-env @babel/preset-react`
  - _babel-loader allows transpiling of JS with Babel and webpack_
  - _@babel/core is the babel compiler_
  - _@babel/preset-env reads all JS syntax_
  - _@babel/preset-react enables babel to read React_
- Include the following in the webpack.config.js

```JS
module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /(node_modules)/,
        use: {
          loader: "babel-loader",
        },
      },
    ],
  },
```

- `touch babel.config.json` and add the following to it _configure babel_

```json
{
  "presets": ["@babel/preset-env", "@babel/preset-react"]
}
```
