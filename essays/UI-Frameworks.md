---
layout: essay
type: essay
title: The Importance of Coding Standards
date: 2016-09-22
labels:
  - Coding Standards
  - ESLint
---

```
function reverseString(string){
let string="";
let returnValue='';
for(let i=string.length;i>=0;i--){
string+=string[i]
}
return string;
}
```

One can see that without the use of coding standards even simple code like this would be difficult to debug and mantain.

```
function reverseString(string) {
  let newString = '';
  for (let i = string.length; i >= 0; i -= 1) {
    newString += string[i];
  }
  return newString;
}
```

however by taking a minute using ESLint with the code it is now much more readable.
	
This benefit to using a coding standard is magnified when working on large projects.  Each individual coder has their own set of rules for code style they were taught, but something like ESLint allows you to have a consistent coding style throughout. The extra time needed to confirm to a coding standard is peanuts next to time that could be saved wasted on trying to understand or debug unclear code.  Powerful tools like ESLint can also can help you clean up your old code, for example flagging variables that are no longer being used.
