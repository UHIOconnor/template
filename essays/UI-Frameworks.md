---
layout: essay
type: essay
title: The Importance of Coding Standards
date: 2016-09-22
labels:
  - Coding Standards
  - ESLint
---
Picking up a UI framework is no easy task and we might ask ourselves why even bother when html is honestly not that difficult. However after putting in the time in a framework like semantic UI the benefits can easily be seen in the code. Semantic UI brings with it powerful library of classes that are modular and make editing a UI element simple. But even more impressive is it accomplishes this through use of easily readable English phrases. If I do not know html even the simplest code can seem difficult especially in a large project for example even a basic image would need a class in the css like

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

```
function reverseString(string) {
  let newString = '';
  for (let i = string.length; i >= 0; i -= 1) {
    newString += string[i];
  }
  return newString;
}
```

