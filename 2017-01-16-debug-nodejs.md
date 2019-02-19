---
published: true
title: Debug tips & tricks for Node js
---

# 2017-01-16-debug-nodejs

A few debug tricks learned the hard way.

## Required module empty

You require a module that when inspecting its value end to be an empty object. You check if the required path is valid \(it should have thrown an error if so but any way\). But after 1-2 hours, I ended typing exactly my problem "Required module empty" and looked at this [stackoverflow](http://stackoverflow.com/questions/23875233/require-returns-an-empty-object/23875299).

It is a circular dependency problem, the required module have required in any way the module that try to require it... So double check your modules architecture.

## update node  to latest version

Here a simple and eficient way for ubuntu servers [https://askubuntu.com/questions/426750/how-can-i-update-my-nodejs-to-the-latest-version](https://askubuntu.com/questions/426750/how-can-i-update-my-nodejs-to-the-latest-version)

