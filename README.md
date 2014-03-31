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
