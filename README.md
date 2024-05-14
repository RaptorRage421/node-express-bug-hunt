# Node & Express Bug Hunt!

**READ ALL INSTRUCTIONS BEFORE STARTING**

There are 10 bugs in total, can you find them all? There are hints throughout (???), you should only need to make minor modifcations to 10 lines of code.

**Don't race through the files looking for the issues!** They should all have a console log or error that help you identify them. Read the console so that you know what error will cause each bug. The last one is tricky since it doesn't throw any errors. Document the error, line number and your fix in this README for each of the bugs.

## Setup
```
npm install
npm start
```

> NOTE: A couple of bugs prevent the server from starting.

## Error List

TODO: Add the error here followed by the line of code you fixed.

### Bug 0

`ReferenceError: app is not defined`

Fixed `quote.router.js` line 28: switch `app` to `router`. _This is the solution to the first bug._

### Bug 1

quote.router.js did not have a `module.exports = router` which was not allowing the module to be required on the server.js as intended. 

### Bug 2

![alt text](<server/public/images/Screenshot 2024-05-13 at 8.48.34 PM.png>)<br>
![alt text](<server/public/images/Screenshot 2024-05-13 at 8.48.42 PM.png>)<br>![alt text](<server/public/images/Screenshot 2024-05-13 at 9.05.09 PM.png>)<br>
url in the Axios call in client.js function getQuotes() was entered incorrectly with a curly bracket at the end. removing this allows the call to happen. <br>

## Extra Practice (Optional)

Complete the JS debugging exercises at:

- https://education.launchcode.org/intro-to-professional-web-dev/chapters/errors-and-debugging/exercises.html
