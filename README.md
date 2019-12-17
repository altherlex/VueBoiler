# coding-interview
Instructions  

- I recommend using NodeJS version 10.15.0 to setup and run this as that is what I was using to set it up.
- Once you have NodeJS installed you should be able to run `npm install` and then `npm run serve` to run the application locally.  
- When the app loads it will be rendering the file App.vue. As you'll notice it is also importing a file called HelloWorld.vue which has a lot of the details you'll see on the screen.
- Your goal is to re-create the screen seen in the screenshot screen.png.
- I recommend trying to do create the form and table in just one file but you could split the form and table into two components if you would like.
- Please don't setup a database, just store the employees list in an array. A side effect of this will be that if you refresh the page the list will empty, that's OK though.
- You don't need to deploy it anywhere, just run it locally and submit the code in a zip file when you're happy with it.
- Make the page look as similar to the screenshot as you can.
- I recommend that you read through some of the Vue documentation but here are a few quick tips:
  - v-for is how you create a for loop in html with Vue (You'll need this for the list)
  - v-on:click is the syntax you can use on the "Add Employee" button to call a function when it is clicked.

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
