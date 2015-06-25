# Paint.css

Paint.css is a pattern library consisting of lightweight, reusable modules for Circle based on [yeti.css](http://yeticss.com/). It has been built to reflect Circle's visual and branding guidelines.

## Table of Contents

* [How To Run](https://github.com/meetcircle/paint.css#how-to-run)
* [Structure](https://github.com/meetcircle/paint.css#structure)
* [How To Include In Your App](https://github.com/meetcircle/paint.css#how-to-include-in-your-app)
* [Custom Fonts](https://github.com/meetcircle/paint.css#custom-fonts)
* [CSS Reset](https://github.com/meetcircle/paint.css#css-reset)
* [Documentation](https://github.com/meetcircle/paint.css#documentation)
* [Contributing](https://github.com/meetcircle/paint.css#contributing)
* [License](https://github.com/meetcircle/paint.css#license)

## How to run?

For development mode:

```
npm install
npm start
```

The demo site will be available at `http://localhost:8080`. You can use the [livereload extension](https://chrome.google.com/webstore/detail/livereload/jnihajbhpnppcggbcgedagnkighmdlei?hl=en) and files will automatically rebuild and reload in the browser when you change them.

## Structure
Paint.css is located in `lib/paintcss` and can be installed through [npm](https://www.npmjs.org/). Variables and mixins can be found in `lib/paintcss/globals` and components in `lib/paintcss/components`. Markup for each component lives in `public/templates`.

Note: installing paint.css **will not** include `assets` or `public`.

```
├── assets
│   ├── logos
│   └── swatches
├── lib
│   └── paintcss
│       ├── components
│       ├── globals
│       └── index.styl
└── public
    ├── css
    ├── images
    ├── js
    ├── styl
    └── templates
```

## How to include in your app

Paint.css is a [Stylus](http://stylus-lang.com/) plugin, so you just need to ensure Stylus knows to use the plugin, and then import it in your app.

Make sure that you have `stylus` available from command line:

```
npm install -g stylus
```

### Static sites

If you are compiling your Stylus with its command line interface, maybe directly or via a Makefile or similar, it's as easy as:

1. `npm install paintcss --save-dev`
2. Add "-u paintcss" to the command: `stylus -u paintcss ./path/to/app.styl`
3. Now you can import paintcss, or a subcomponent of paintcss, in your app's .styl files:

    ```stylus
    @import 'paintcss'
    // or
    @import 'paintcss/components/type'
    ````

### Single page apps using moonboots

The simplest way to include Paint.css in a moonboots app is to use [stylizer](https://github.com/latentflip/stylizer);

1. `npm install paintcss --save`
2. Add 'paintcss' to the list of plugins in stylizer in your beforeCSS moonboots build step:

    ```javascript
    beforeBuildCSS: function (done) {
        var plugins = ['paintcss'];

        if (config.isDev) {
            stylizer(stylesheetsDir + '/app.styl', stylesheetsDir + '/app.css', plugins, done);
        }
    },
    ```

3. Import Paint.css or a submodule of Paint.css in your app's .styl files:

    ```stylus
    @import 'paintcss'
    //or
    @import 'paintcss/components/type'
    ```

### Version Pinning

It's __**strongly**__ recommended that you pin to a specific version of paint.css, so that updates to the styleguide don't break your site. To do that, reference a specific tagged release in your package.json by appending #<tagname> to the git url, e.g.:

    ```js
        //package.json

        {
            //...
            "dependencies": {
                "paintcss": "git+ssh://git@github.com/meetcircle/paint.css#v0.1.0"
            },
            //...
        }
    ```

You can see the list of available releases at: [https://github.com/meetcircle/paint.css/releases]().

## Custom fonts
Paint.css defines [Gotham Rounded](http://www.typography.com/fonts/gotham-rounded/overview/) as the default typeface. Use Typography.com to set up font serving accordingly or change the typeface variables [here](https://github.com/meetcircle/paint.css/blob/gh-pages/lib/paintcss/globals/_variables.styl#L13-L14).


## CSS Reset

A CSS reset is **included** in Paint.css by default (namely [normalize.css](https://github.com/necolas/normalize.css)).

## Documentation
Documentation and examples of usage can be found on [http://meetcircle.github.io/paint.css]().


## Contributing
See the [CONTRIBUTING.md](https://github.com/meetcircle/paint.css/blob/gh-pages/CONTRIBUTING.md) for information on how to contribute to yeti.css.

## License
MIT
