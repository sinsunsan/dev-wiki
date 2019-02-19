---
published: true
title: Debug tips & tricks for Angular 2
---

A few debug tricks learned by the ways.

### Screen debug with | json pipe

You can use Augury but some time a simple in screen debug is convenient.

You can do it thanks to the json pipe that transform json objects in string.    

`my object | json`    

It is convenient for forms where we want to see the consequence of your actions. And track the form state.

Using html PRE tag allow to display the json with line break.


````
<div style="margin-top: 20px" *ngIf="f">
	<div>Form details:-</div>
	<pre>Is form valid?: <br>{{f.valid | json}}</pre>
	<pre>Is form submitted?: <br>{{f.submitted | json}}</pre>
	<pre>submitted value: <br>{{f.value | json}}</pre>
</div>
````

### Augury

[https://augury.angular.io/](https://augury.angular.io/)

Augury is a more complete debug utility for chrome.
It can display the state of variable in each component.


### Print json object and paste in a text editor 

````
copy(JSON.stringify(changes.widgetData.currentValue, null, 2))
````
It copy the result of JSON.stringify with the option to set correct identation 2.


### Access file by filename to add break point 

In chrome debugger go to sources tab and type 
CMD + P (same short cut that in sublime text)
it open a list of files 

<img src="../images/chrome-debugger-file-list.png" alt="chrome file list debugger">

### Debug on mobile 

Use the [chrome debugger remote device](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/?utm_source=dcc&utm_medium=redirect&utm_campaign=2016q3) feature with an adroid