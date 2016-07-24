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

# Customizing Bootstrap

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


# References
[Creating a Custom Bootstrap Build With SCSS - Trey Hunner](https://www.codementor.io/development-process/tutorial/create-custom-bootstrap-build-with-scss)
