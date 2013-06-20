# WHY AMD?



# AMD

- Asynchronous 
- Module 
- Definition



**Asynchronous module definition (AMD)** is a JavaScript API for defining modules such that the module and its dependencies can be asynchronously loaded. 

([Wikipedia](http://en.wikipedia.org/wiki/Asynchronous_module_definition))



![AMD](http://upload.wikimedia.org/wikipedia/commons/6/66/Asynchronous_Module_Definition_overview.png)



## Should we adopt it?
- There are many different ways for organizing and loading client-side JavaScript
- AMD is only one of many



## Depends...
- From the project
- And from personal taste



As a **javascripter** I am not a big fan of the **Rails Asset Pipeline**.



# Why?



1. It is not truly modular and there is no implicit way of protecting variables from the global name space.



### Does this really matter?



As usual it depends...

One could correctly argue that there is no big chance of variable names such as **backbone** or **jquery** conflicting, 

- but things are more subtle than how they appear...



```js

//= require_tree .

var roundToDecimals = function(number, places) {
    // more code
};

var addCommasToNumber = function(number) {
    // more code
};
```

([ mypolygon-v2 - application.js](https://github.com/unepwcmc/mypolygon-v2/blob/master/app/assets/javascripts/application.js))

These are global variables, with very generic names.

Still not a big issue? Maybe, but as the application grows chances are that name conflicting risks grow too... **and there is something worse...**



This way of organizing code does not help to keep things tidy... and maintainable. 
Every single piece of functionality should have its right place inside an application. 
`roundToDecimals`, for example, could live in a reusable, generic utility number-functions module. This can obviously be done in the Asset Pipeline too, but it is not an enforced practice, so one, in the hurry of the moment, ends up writing messy code.


