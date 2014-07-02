# gulp-csscomb

> Format CSS coding style with [CSScomb](https://npmjs.org/package/csscomb).

*If you have any difficulties with the output of this plugin, please use the
[CSScomb tracker](https://github.com/csscomb/csscomb.js/issues).*

## Installation

Install via [npm](https://npmjs.org/package/gulp-csscomb):

```
npm install gulp-csscomb --save-dev
```

## Example 1

```javascript
var gulp = require('gulp');
var csscomb = require('gulp-csscomb');

gulp.task('styles', function () {
    return gulp.src('src/styles/main.css')
        .pipe(csscomb())
        .pipe(gulp.dest('./build/css'));
});
```

## Example 2

```javascript
var gulp = require('gulp');
var less = require('gulp-less');
var prefixer = require('gulp-autoprefixer');
var csscomb = require('gulp-csscomb');

gulp.task('styles', function () {
    return gulp.src('src/styles/bootstrap.less')
        .pipe(less({strictMath: true}))
        .pipe(prefixer([
            'Android 2.3',
            'Android >= 4',
            'Chrome >= 20',
            'Firefox >= 24', // Firefox 24 is the latest ESR
            'Explorer >= 8',
            'iOS >= 6',
            'Opera >= 12',
            'Safari >= 6']))
        .pipe(csscomb())
        .pipe(gulp.dest('./build/css'));
});
```

If there is `.csscomb.json` file present in the same folder as the source file(s),
`csscomb` will read config settings from it instead using default config.

## License

The MIT License (MIT) © Konstantin Tarkus ([@koistya](https://twitter.com/koistya))