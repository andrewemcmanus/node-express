# node-express

Node provides a way of using Javascript as a back-end language, and it allows for connecting files together via dependencies. It requires setting up a package.json file that serves as an entry point for the project.

```
npm init
```
This creates a package.json file, prompting the user for several different parameters, and creates a set of objects containing those parameters.

```
npm init -y
```

This is a shortcut that fills in default parameters for package.json.

If we create two files, ```index.js``` and ```myModule.js```, we can connect them in the following ways. If we add this to ```myModule.js```:

```
module.exports.meanGirls = () => "I'm a mouse, duh!"
```
...then we can run that function in ```index.js``` by doing this:

```
const.myModule = require('./myModule.js');
mymodule.beBasic();
```
If we want to create multiple functions in myModule.js for use in index.js, we can do the following in myModule.js:

```
function gretchen() {
  let quote = "I don't think my father, the inventor of toaster strudel, would appreciate that."
  return quote;
}

function add(num1, num2) {
  return num1 + num2;
}

function subtract(num1, num2) {
  return num2 - num1;
}
function addAgain(num1, num2) {
  return num1 + num2;
}
module.exports = {
  meanGirls,
  gretchen,
  add,
  subtract
};
```
...and this in index.js:

```
const {meanGirls, gretchen} = require('/myModule.js');
console.log(gretchen());
```
**Is there a JS6 issue here? I got messages asking me to revise it. Some of this code is incorrect...**
