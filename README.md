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


# References
[Creating a Custom Bootstrap Build With SCSS - Trey Hunner](https://www.codementor.io/development-process/tutorial/create-custom-bootstrap-build-with-scss)
