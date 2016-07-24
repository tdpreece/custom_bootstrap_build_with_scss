The following describes how I went about customising bootstrap using
Scss.
I tried to do this with as few dependencies as possible so that I could
focus on the subject.  In production I'd use [Gulp](http://gulpjs.com/)
to automate the build process.

# Prerequisites
* Node

# Setting up
I created a new directory for this project then crated a new node 
project by running a the following command and hitting enter when 
presented with questions.


```
mkdir custom_bootstrap_build_with_scsss
npm install bower
```

Install node-sass, which will compile .scss files to css.

```
npm install --save node-sass
```

I then installed [Bower](https://bower.io/) a package manager for 
front-end components.

```
npm install --save bower
```

I created a bower.json file by running the following command and hitting
enter when presented with questions.

```
./node_modules/bower/bin/bower init
```

Installed Bootstrap using Bower.
```
./node_modules/bower/bin/bower install --save bootstrap-sass
```

# Building the css from scss

I created a scss file for my site.

```
mkdir scss
```

./scss/site.scss
```
@import "bootstrap";
@import "bootstrap/theme";
```

I built the the css.

```
mkdir css
./node_modules/node-sass/bin/node-sass --include-path ./bower_components/bootstrap-sass/assets/stylesheets -o css scss/
```

This produced the ./css/site.css file.

# Customizing Bootstrap

Bootstrap can be customized by setting variables, which will take 
presedence to Bootstrap's defaults.  A list of these variables can be 
found in `./bower_components/bootstrap-sass/assets/stylesheets/bootstrap/_variables.scss`

I wanted to change the colour of the primary buttons so I needed to 
specify a new colour for the $btn-primary-bg variable.

I created a [partial SCSS file](http://sass-lang.com/guide#topic-4) to 
store my variables.
./scss/_variables.scss

```
$btn-primary-bg: #ff2828;
```

I then imported the _variables.scss in site.scss

./scss/site.scss

```
@import "variables";
@import "bootstrap";
@import "bootstrap/theme";
```

variables has to be included before bootstrap because way bootstrap goes
about letting you 'override' variables.  In `./bower_components/bootstrap-sass/assets/stylesheets/bootstrap/_variables.scss`
you'll notice that variable definitions are followed by [`!default`](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#variable_defaults_), 
which means that the variable is only assigned if it hasn't already been
assigned.

```
$btn-primary-color:              #fff !default;
$btn-primary-bg:                 $brand-primary !default;
$btn-primary-border:             darken($btn-primary-bg, 5%) !default;`
 
```


I then re-built the site css file and opened it up to check that my 
changes had been applied.

./css/site.css
```
...
.btn-primary {
  color: #fff;
  background-color: #ff2828;
  border-color: #ff0f0f; }
...
```

# References
[Creating a Custom Bootstrap Build With SCSS - Trey Hunner](https://www.codementor.io/development-process/tutorial/create-custom-bootstrap-build-with-scss)
