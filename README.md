# grunt-datauri-variables

[![Build Status](https://travis-ci.org/davemo/grunt-datauri-variables.png?branch=master)](https://travis-ci.org/davemo/grunt-datauri-variables)


> Generates .scss datauri variables for .{png,gif,jpg} and .svg

## Intended Use

Taking _small_ images and inlining base64 encoded versions of them in your stylesheets to avoid additional HTTP requests. This also allows you to eliminate image sprites from your workflow.

## Why would I use this?

If you need a very small task with limited dependencies this task is for you. If you want more robust options you may want to check out [grunticon](https://github.com/filamentgroup/grunticon).

## How would I integrate this task?

## Getting Started
This plugin requires Grunt `~0.4.1`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-datauri-variables --save
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-datauri-variables');
```

## The "datauri" task

### Overview
In your project's Gruntfile, add a section named `datauri` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  datauri: {
    options: {
      varPrefix: '', // defaults to `data-image-`
      varSuffix: ''  // defaults to empty string
    },
    your_target: {
      files: {
        src: "images/**/*.{png,jpg,gif,svg}"
        dest: "generated/_datauri_variables.scss"
      }
    },
  },
})
```

### Sample Output

Given the configuration in the Overview section above, you can expect `grunt datauri` to output the following to `generated/_datauri_variables.scss` (lines truncated for brevity).

```shell
cat generated/_datauri_variables.scss

$data-image-alert: "data:image/png;base64,iVBORw0KGgoAAAANSUhEUg...";
$data-image-blurry: "data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAA...";
$data-image-circle: "data:image/gif;base64,R0lGODlhCwALAPEAAAAAA...";
$data-image-truck: "data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj...";
```

### Options

#### options.varPrefix
Type: `string`
Default value: `data-image-`

A prefix prepended to the .scss variable name for the image.

#### optins.varSuffix
Type: `string`
Default value: ''

A suffix appended to the .scss variable name for the image.

## Running Specs

* clone this repo
* `npm install`
* `grunt spec`

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).

## License

MIT
