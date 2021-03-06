# JSDoc Docio Template

A blue [JSDoc](http://usejsdoc.org/) template theme (based off [docstrap](https://github.com/terryweiss/docstrap),[jsdoc-oblivion](https://github.com/miguelmota/jsdoc-oblivion)).

# Install

Available via [npm](https://www.npmjs.org/)

```bash
npm install jsdoc-docio
```

Available via [bower](http://bower.io/)

```bash
bower install jsdoc-docio
```

# Usage

[Grunt](http://gruntjs.com/) dependencies:

```bash
npm install jsdoc --save-dev
npm install grunt-jsdoc --save-dev
```

`gruntfile.js`:

```javascript
module.exports = function (grunt) {
  grunt.initConfig({
    pkg: grunt.file.readJSON('package.json'),
    jsdoc : {
      dist : {
        src: [
          './**/*.js',
          'README.md'
        ],
        jsdoc: './node_modules/.bin/jsdoc',
        options: {
          destination: 'docs',
          configure: './config/conf.json',
          template: './node_modules/jsdoc-docio/template'
        }
      }
    }
  });
  grunt.registerTask('default', ['jsdoc']);
  grunt.loadNpmTasks('grunt-jsdoc');
};
```

`config/conf.json`:

```json
{
  "tags": {
    "allowUnknownTags": true
  },
  "source": {
    "includePattern": ".+\\.js(doc)?$",
    "excludePattern": "(^|\\/|\\\\)_"
  },
  "plugins": [],
  "templates": {
    "cleverLinks": false,
    "monospaceLinks": false,
    "default": {
      "outputSourceFiles": true
    },
    "systemName"      : "Docio",
    "footer"          : "",
    "copyright"       : "Copyright © 2017",
    "navType"         : "vertical",
    "theme"           : "docio",
    "linenums"        : true,
    "collapseSymbols" : false,
    "inverseNav"      : true
  }
}
```

Generate:

```bash
grunt jsdoc
```
