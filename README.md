# Leedian JsDoc Template

## Installation

```
npm i gulp-cli -g
npm i gulp --save-dev
npm i leedian-jsdoc --save-dev
```

## Usage

gulpfile.js
```
var gulp = require('gulp');
var jsdoc = require('leedian-jsdoc');

gulp.task('default', function (cb) {
    gulp.src(['./README.md', './*.js'], { read: false })
        .pipe(jsdoc(cb));
});
```

You can also pass in your own config to override the defaults

conf.json
```
{
    "tags": {
        "allowUnknownTags": true
    },
    "source": {
        "includePattern": ".+\\.js(doc)?$",
        "excludePattern": "(^|\\/|\\\\)_"
    },
    "opts": {
        "recurse": true
    },
    "templates": {
        "cleverLinks": true,
        "monospaceLinks": true,
        "default": {
            "outputSourceFiles": true
        },
        "applicationName": "My SDK",
        "openGraph": {},
        "meta": {}
    }
}
```
gulpfile.js
```
gulp.task('default', function (cb) {
    var config = require('./conf.json');
    gulp.src(['./README.md', './*.js'], { read: false })
        .pipe(jsdoc(config, cb));
});
```


