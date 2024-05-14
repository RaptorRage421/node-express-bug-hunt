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

## Bug 0

`ReferenceError: app is not defined`

Fixed `quote.router.js` line 28: switch `app` to `router`. _This is the solution to the first bug._


## Bug 1

quote.router.js did not have a `module.exports = router` which was not allowing the module to be required on the server.js as intended. 

## Bug 2
server.js line 17. `app.use(express.static('public'))` this needs to be changed to `app.use(express.static('server/public'))`<br>
![alt text](<server/public/images/Screenshot 2024-05-13 at 9.59.21 PM.png>)![alt text](<server/public/images/Screenshot 2024-05-13 at 9.59.27 PM.png>)

## Bug 3
client.js line 7 remove the `}` from the url<br>
![alt text](<server/public/images/Screenshot 2024-05-13 at 8.48.34 PM.png>)<br>
![alt text](<server/public/images/Screenshot 2024-05-13 at 8.48.42 PM.png>)<br>![alt text](<server/public/images/Screenshot 2024-05-13 at 9.05.09 PM.png>)<br>
url in the Axios call in client.js function getQuotes() was entered incorrectly with a curly bracket at the end. removing this allows the call to happen. <br>

## Bug 4
quote.router.js line 8: switch `/quotes` to `/`<br>
![alt text](<server/public/images/Screenshot 2024-05-13 at 9.10.16 PM.png>)<br>
The app.use route is set to /quotes<br>
![alt text](<server/public/images/Screenshot 2024-05-13 at 9.13.11 PM.png>)<br>
AND the quote.router.js `router.get` is also currently set to /quotes<br>
![alt text](<server/public/images/Screenshot 2024-05-13 at 9.13.23 PM.png>)<br>
This makes it look for /quotes/quotes which doesn't exist. Removing the quotes from the quote.router.js file route will get this to function correctly.

## Bug 5
quote.router.js line 5: switch `quoteList = {}` to `quoteList = []`<br>
![alt text](<server/public/images/Screenshot 2024-05-13 at 9.18.10 PM.png>)<br>
GET throws an error.  <br>
![alt text](<server/public/images/Screenshot 2024-05-13 at 9.18.26 PM.png>)<br>
quotesFromServer is not iterable. This is because the data being sent is an Object and not an Array. <br>![alt text](<server/public/images/Screenshot 2024-05-13 at 9.18.34 PM.png>)<br>
making this an Array resolves this bug. 

## Bug 6
quote.router.js Line 21: `quotesList.push(quoteToAdd)`, the storage locations is `quoteList` simply remove the 's'<br>
![alt text](<server/public/images/Screenshot 2024-05-13 at 11.06.11 PM.png>)

## Bug 7
client.js line 52: switch `getQuote()` to `getQuotes()`<br>
Attempting to Submit a new Quote. The console log shows that we are entering the submitForm function, but there is an error. getQuote is not defined.  This is a typo on a call to the getQuotes() function. <br>
![alt text](<server/public/images/Screenshot 2024-05-13 at 9.24.39 PM.png>)![alt text](<server/public/images/Screenshot 2024-05-13 at 9.26.50 PM.png>)

## Bug 8
client.js Line 16: `let i=0;` i is not needed in this loop, because it is written as a for of loop, so this code is doing nothing. 
client.js Line 24: `i+=1` again this code does not provide any functionality. 

## Bug 9


## Bug 10


## Extra Practice (Optional)

Complete the JS debugging exercises at:

- https://education.launchcode.org/intro-to-professional-web-dev/chapters/errors-and-debugging/exercises.html