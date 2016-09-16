---
layout: essay
type: essay
title: Igniting the fire
date: 2015-08-26
labels:
  - Software Engineering
  - Learning
---

Git: Configuration Management the Right Way
	Configuration management is one of the key tenants of software engineering. Without a system to manage contributions between team members, larger software projects would simply not be possible. The need to coordinate changes and versions between developers has driven the development of various styles of configuration management.  Each style seeks to solve three fundamental problems
	The Double Maintenance Problem –  one should only have to have to update one file.
	The Shared Data Problem – a file must be able to be accessed by multiple developers at once.
	The Simultaneous Update Problem - a problem arising when a file is updated multiple times simultaneously.
CVS tried to solve these problems using a single repository which multiple developers had access to. To solve collisions developers could lock a file to work on to ensure that integrity is maintained. In practice however this execution is inherently clunky and slows down the project. Having worked mainly with this practice before I have had many cases where having parts of the project locked off to me needlessly complicates the project.
	Git however elegantly solves this by allowing each developer to maintain their own repository. Each developer can than chose when they want to pull other peoples updated files or push their own changes. This allows Git to maintain system integrity while still giving the individual developer complete freedom to make changes. While part of GitHub’s success may be due to being one of the largest sources of open source software I definitely feel that its success is due to how much Git facilitates the development of open source software. From my past experiences with CVS styles I am definitely looking forward to the flexibility Git provides.


