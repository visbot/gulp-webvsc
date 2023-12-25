# gulp-webvsc

[![License](https://img.shields.io/npm/l/gulp-webvsc?style=for-the-badge)](https://github.com/idleberg/gulp-webvsc/blob/main/LICENSE)
[![Version](https://img.shields.io/github/v/release/idleberg/gulp-webvsc?style=for-the-badge)](https://github.com/idleberg/gulp-webvsc/releases)
[![Build](https://img.shields.io/github/actions/workflow/status/idleberg/gulp-webvsc/default.yml?style=for-the-badge)](https://github.com/idleberg/gulp-webvsc/actions)

Gulp plugin to convert [Winamp AVS presets](https://www.wikiwand.com/en/Advanced_Visualization_Studio) into [Webvs](https://github.com/azeem/webvs) JSON.

## Installation

```sh
$ npm install --save-dev gulp-webvsc
```

## Usage

`webvsc([options])`

The output file-extension will automatically be set to `.webvs`, so there's no need to pipe in additional plugins.

**Example:**

Standard usage

```js
import gulp from 'gulp';
import { webvsc } from 'gulp-webvsc';

gulp.task('convert', done => {
	gulp.src('input/**/*.avs')
		.pipe(webvsc())
		.pipe(gulp.dest('output'));

	done();
});
```

## Options

### hidden

Type: `boolean`  
Default: `true`  

Don't extract hidden strings from fixed-size strings

### minify

Type: `boolean`  
Default: `false`  

Minify generated JSON

### noDate

Type: `boolean`  
Default: `false`  

Does not add `date` property to generated JSON

### verbose

Type: `number`  
Default: `0`  

Control the amount of output displayed:

* `0` Hide output
* `1` List detected components
* `2` List component details

## Related Projects

* [webvsc](https://github.com/grandchild/AVS-File-Decoder)
* [webvsc-cli](https://github.com/idleberg/webvsc-cli)
* [grunt-webvsc](https://github.com/idleberg/grunt-webvsc)

## License

This work is licensed under [The MIT License](https://opensource.org/licenses/MIT)
