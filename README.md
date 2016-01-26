# NOTE !!!
Brunch 2.2.0 introduces a new way to write plugins, so use brunch 2.1.3 untill we get a chance to update (and figure out how to best handle backwards compatability). See [this issue](https://github.com/madsflensted/elm-brunch/issues/11)
 

# elm-brunch
[Brunch](http://brunch.io) plugin to compile Elm code

# Install Elm
[Elm instalation instructions](http://elm-lang.org/Install.elm)

# Tips
Update the "source-directories" property in the elm-package.json file if you want to compile multifile elm projects.
Then configure elm-brunch:

```
  // Configure your plugins in brunch-config.js (or .coffee)
    plugins: {
      ...

      elmBrunch: {
        // Set to path where elm-package.json is located, defaults to project root (optional)
        // if your elm files are not in /app then make sure to configure paths.watched in main brunch config
        elmFolder: 'path/to/elm-files',
        // Set to the elm file(s) containing your "main" function
        // `elm make` handles all elm dependencies (required)
        // relative to `elmFolder`
        mainModules: ['source/path/YourMainModule.elm'],
        // Defaults to 'js/' folder in paths.public (optional)
        outputFolder: 'some/path/'
      }
   }

```

The output filename is the lowercase version of the main module name:
```
YourMainModule.elm => outputFolder/yourmainmodule.elm
```

# Examples
The following repos are examples of elm-brunch configuration:
- https://github.com/joedski/brunch-with-elm/blob/master/brunch-config.coffee
- https://github.com/madsflensted/dots/blob/master/brunch-config.js
- https://github.com/ivanoats/Bingo/blob/master/brunch-config.js
