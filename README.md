# hl-training-sass
Healthline Friday Lunch Training SASS mixins
6/17/16

used this tutorial:

Twitter Bootstrap v3 - npm, sass, gulp
http://www.codevoila.com/post/32/customize-bootstrap-using-bootstrap-sass-and-gulp

and

http://sass-lang.com/guide

1 Initialize A Project

$ cd customize-bootstrap-sass
$ npm init

Then install npm packages we will used later.

$ npm install gulp -g --save-dev
$ npm install bootstrap-sass --save-dev
$ npm install gulp-sass --save-dev

Now your customize-bootstrap-sass/package.json file should include following dependencies like this:

Explanation:

bootstrap-sass is the package of Bootstrap scss source code. We're going to override some variables and rebuild the Scss source.

gulp-sass, package tool for Gulp to compile .scss code to css.

2 Project Folder Structure

2.1 Folders

Folder structures as follows:

Addtionally, bootstrap-sass had been installed under node_modules folder.


Scss source files are all under node_modules/bootstrap-sass/assets/stylesheets/

_bootstrap.scss is the entry file. Open it you can see this file imported various source scss codes of different Bootstrap components.


2.2 gulpfile.js

Configure gulpfile.js according to our folder structure.

2.2.1 Require Modules

The first step, require modules:

2.2.2 src and dist

The second step, specify source folder and distribution folder.

Pay attention to includePaths, this will tell gulp-sass where to import scss files.

2.2.3 Fonts Task

The third step, add a gulp fonts task to copy bootstrap required fonts to dist folder:

2.2.4 Sass Task

The fourth step, compile source scss into css and copy the result css file to dist:

['fonts'] means sass task will depend on fonts task, before executing sass task gulp will automatically run fonts task firstly.

