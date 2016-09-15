less-plugin-npm-import-reloaded
========================

Fork of [less-plugin-npm-import](https://github.com/less/less-plugin-npm-import) with feature for specifying base directory added from [unmerged pull request](https://github.com/less/less-plugin-npm-import/pull/19). Original module adds the ability for less to import from npm packages.

## lessc usage

Install with npm

```bash
npm install -g less-plugin-npm-import
```

In less file:

```
@import "npm://packagename/path/to/file.less";
```

or if importing a css file an [import option](http://lesscss.org/features/#import-options) is required:

```
@import (less) "npm://packagename/path/to/file.css";
```

css/less extensions not necessary

Options:  
prefix - default: npm://
basedir - allow setting the basedir node modules should be resolved from.

## Command line usage

```
lessc --npm-import file.less file.css
lessc --npm-import="prefix=~" file.less file.css
lessc --npm-import="basedir=/usr/local/path" file.less file.css
```

## Programmatic usage

```
var NpmImportPlugin = require("less-plugin-npm-import"),
    options = { plugins: [new NpmImportPlugin({
      prefix: '~',
      basedir: __dirname
    })] };
less.render(css, options)
    .then(...
```

## Browser usage

Browser usage is not supported.

Testing
-------

run the tests by running `node test`
You require the dev dependencies installed (which includes less)
