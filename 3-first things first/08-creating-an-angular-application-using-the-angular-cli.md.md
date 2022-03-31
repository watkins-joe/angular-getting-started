creating an angular application using the angular CLI

ng is not recognized, it's not a global command

to use the ng command directly, we need to install it **globally**

in order to do this, we go open a terminal or command prompt window and enter the command:

`npm i -g @angular/cli`

breakdown of command
- `npm`
    - base/root node package manager command
- `i`
    - subcommand for npm, shorthand for `install`
- `-g`
    - global flag, tells npm to install whatever package we are installing globally instead of locally in a certain directory
- `@angular/cli`
    - denotes which package we want to install

with the CLI installed globalled, we can now use the `ng` command from anywhere

we had to add paths to our environment variables for windows. specifically, in the `Path` user variables, we had to add the paths

- `%USERPROFILE%\AppData\Roaming\npm`
- `%USERPROFILE%\AppData\Roaming\npm\node_modules\@angular\cli\bin`

then, our command to create a new angular app using the CLI worked as expected

we used the following command to create a new angular app using the CLI:

`ng new apm-new --prefix pm`

breakdown of command
- `ng`
    - base/root angular CLI command
- `new`
    - subcommand to create a new angular application
- `apm-new`
    - the desired name of the new angular application
- `--prefix`
    - allows us to define a prefix for the command, prefix follows this command
- `pm`
    - prefix for the command, short for `product management`

CLI asks us several questions

1. Would you like to add Angular routing? (y/N)
    - will learn more about this and will likely update this area in the future.
2. Which stylesheet format would you like to use?
    - allows us to choose the stylesheet format we want to use, between default CSS, SCSS, Sass, and Less.

the CLI then begins the setup for the new application, as well as creates the new package.json file.

we can now navigate down the new apm-new folder we just created.

once the packages are finished installing, run npm start to start up a server and view our new application.