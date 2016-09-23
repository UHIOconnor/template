---
layout: essay
type: essay
title: The Importance of Coding Standards
date: 2016-09-22
labels:
  - Coding Standards
  - ESLint
---



Coding standards may seem like an unnecessary hassle when one is starting out with code. This can seem especially true when using tools like ESLint as it constantly flags tiny mistakes.  And while it might seem frivolous when one is writing small projects that only a small amount of people will see, one must keep the bigger picture in mind. Enforcing coding standards improves the codes readability allowing the purpose of a line of code to be more easily grasped or to facilitate debugging the code.  ESLint further improve this by enforcing a standard that even someone who has just picked up the language with habits gained in another language can write in a widely used standard.
	
Take for example the following code
	function reverseString(string){
	let string="";
	let returnValue = '';
	for(let i=string.length;i >= 0;i--){
	string+= string[i]
	}
	return string;
	}
	
This benefit to using a coding standard is magnified when working on large projects.  Each individual coder has their own set of rules for code style they were taught, but something like ESLint allows you to have a consistent coding style throughout. The extra time needed to confirm to a coding standard is peanuts next to time that could be saved wasted on trying to understand or debug unclear code.  Powerful tools like ESLint can also can help you clean up your old code, for example flagging variables that are no longer being used.
