# gulp-pipelog
simple gulp wrapper for pipelog

## Install
Install it by typing

```
npm install gulp-pipelog
```

## Usage
```javascript
var gulp = require("gulp");
var gulpPipelog = require("gulp-pipelog");

gulp.task("myTask",function(){
    var stream = gulp.src(["./test/1.md","./test/2.md","./test/3.md"])
        .pipe(gulpPipelog("this message should appear 3 times","info","forEach"))
        .pipe(gulpPipelog("this warn message should appear once in between the three info messages","warn","atStart"))
        .pipe(gulpPipelog("this OK! message should appear once at the End","ok","atEnd"));
    return stream;
});
```

## Why this wrapper?
This wrapper wraps pipelog:

```javascript
var gulpPipelog = require("pipelog").stream;
module.exports = gulpPipelog;
```

The difference between using this module vs pipelog directly is that this one supports setups that rely
on the "gulp-*" module naming. 