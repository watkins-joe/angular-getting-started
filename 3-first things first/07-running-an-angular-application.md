running an angular application

use `npm start`

when we type that, it will execute ths command `ng serve -o`

breakdown
- ng
    - executes Angular CLI
- serve
    - CLI command, serve builds the app and starts a local web server that lets us serve the app w/o deploying it
- -o
    - command option, opens the URL of the server in our default browser

angular does NOT support IE

when we change our code in our IDE, our code get re-compiled and updates our local server nearly immediately. our changes are reflected in the browser in real time.

to stop the server, press CTRL + C, and then 'y' for yes.

to restart the server, run `npm start` again.

now, we'll learn how to create a new angular application.