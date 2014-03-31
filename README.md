This is an [AngularJS](http://angularjs.org/) module that makes it easy to display loading and error messages in your app. It uses a simple pattern for comminucating loading/error statuses leaving all decisions about the visual presentation of these items up to the developer.

## Install it
If you're familar with how to include third-party modules in AngularJS, then you can probably skip this section. If you're new to the framework, this should help.

### Step 1
Copy the `angular-fully-loaded.js` file from this repository into your project. In this example, I'm using the directory '/js/lib' for the location. My main AngularJS app in this case is in `/js`.

![Screenshot of files in project folder](https://raw.githubusercontent.com/projectweekend/angular-fully-loaded/master/screenshots/copy-files-into-project.png)

### Step 2
Include the file before the main app file:

~~~html
<script src="/js/lib/angular-fully-loaded.js"></script>
<script src="/js/app.js"></script>
~~~

### Step 3
Add `angular-fully-loaded` to the app requirements (`/js/app.js`).
~~~javascript
var app = angular.module('myApp', [
    'myApp.controllers',
    'myApp.filters',
    'myApp.services',
    // 3rd party dependencies
    'angular-fully-loaded'
]);
~~~

## Use it
This module creates two custom directives (tags) that can be used anywhere in your templates. 

### Loading Directive
The loading directive has two attributes that must be populated:

* **data** - This attribute must be bound to a property in your controller. This property must be an object with a booloean property of its own named `loading`. Toggling the value of `loading` from a controller or service will cause the message to show/hide.
* **template** - This is the path to the HTML template the controls the presentation of the loading message.

#### Loading Controller Example
~~~javascript
var cMod = angular.module( 'myApp.controllers', [] );

cMod.controller( 'MyCoolCtrl', function ( $scope ) {

    $scope.SomethingThatLoadsData = {
        status: {
            loading: false // toggle this to true anywhere you wait
        }
    };

} );
~~~


#### Loading Template Example
~~~html
<fl-loading data="SomethingThatLoadsData.status" template="fully-loaded/my-loading-template.html"></fl-loading>

<!--
    This script tag holds the HTML for the loading message.
    It can be placed in any page the Angular app will load.
    I like to place mine in the index page so it gets cached early.
-->
<script type="text/ng-template" id="fully-loaded/my-loading-template.html">
    <p>This is my loading message</p>
</script>
~~~

### Error Directive
Coming soon...
