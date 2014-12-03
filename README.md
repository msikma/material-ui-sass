material-ui-sass
================

This is the [Sass](http://www.sass-lang.com) counterpart of the [material-ui](https://github.com/callemall/material-ui) CSS framework, which is originally written with [Less](https://github.com/callemall/material-ui).

## Installation

Download this repo and copy the [material-ui](material-ui) directory into your project, usually where you put your styles.

## Usage

Import `material-ui/main` into your main `.scss` file, then render Sass as always. For example:

```scss

@import "material-ui/main";

/* Your style here */
h1 {
    text-decoration: blink;
}

```

You can customize the default values overriding those in [custom-variables.scss](material-ui/variables/custom-variables.scss). Include them before importing material-ui: 

```scss

@import "my-custom-variables";
@import "material-ui/main";

/* Your style here */
h1 {
    text-decoration: blink;
}

```

### Use with autoprefixer

I strongly suggest to use [autoprefixer](https://github.com/postcss/autoprefixer) when rendering the final CSS.

## Contribute

I will try to keep the two framworks in sync, but you can also help :-)
If you find bugs or idea for improvements, feel free to [add a new issue](https://github.com/gpbl/material-ui-sass/issues/new).

If you'd like to send pull requests, please try to adopt the current styles and conventions. For now, they need to be close to the [original less code](https://github.com/callemall/material-ui/blob/master/src/less). 

### Development environment 

When converting to Sass, I've found the material-ui [docs site](https://github.com/callemall/material-ui/tree/master/docs) useful to preview my changes. After starting the doc site server, a watching gulp task overwrites the site's `main.css` with the Sass-compiled version. (This means you may need to sassify also the documentation site)

#### Start the documentation site

After running `npm install`, start the documentation site from the `node_modules` directory:

```bash
cd node_modules/material-ui/docs
npm install
gulp
```

PS. Make sure you have [Ruby](https://www.ruby-lang.org/en/downloads/) and [Sass](http://sass-lang.com/install) installed.

#### Start the watch task

Open another tab/windows of the terminal, and run

```
gulp
```

This will watch `./docs/main.scss` file to overwrite the CSS used by the documentation site. While editing our Sass files, you will see a live preview of our changes.
