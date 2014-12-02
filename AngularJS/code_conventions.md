# AngularJS Code Conventions

## Files and Folders

All file and folder names must use lower case characters with words separated by hyphten character.

**Example:**
```
admin-dashboard
admin-details.js
admin-guide.txt
```

## Module separation

Define AngularJS modules using a break down structure to promote separation of concerns.

**Example:**
```shell
\--	users
	|-- create
		|-- create.mdl.js
		|-- create.ctrl.js
		\-- create.tpl.js
	\-- details
		|-- details.mdl.js
		|-- details.ctrl.js
		\-- details.tpl.js
```

Each defined module must be registered with a bottom-up approach.

## AngularJS Units

### Naming convention

When creating AngularJS unit such as controllers, directives, filters, etc. You must add a prefix to the extension to identify what kind of unit the file describes.

| Unit type  | Example					|
|:----------:|:-------------------------|
| Module     | *users-manager.mdl.js*   |
| Service    | *users.srv.js* 			|
| Controller | *user-details.ctrl.js*   |
| Template   | *user-details.tpl.html*  |
| Directive  | *gravtar-picture.drv.js* |
| Factory    | *accounts.fct.js*      	|
| Filter     | *online-users.fltr.js*   |
| Constant   | *status-code.cnst.js*    |
| Value      | *pi.val.js*      		|
| Provider   | *auth-scheme.prv.js*     |
| Decorator  | *site-theme.dcr.js*      |
| Style  	 | *user-details.scss*      |

**Note:** Style files are the only exception to this rule.

### 1 Unit 1 File

Each file must contains just a single AngulaJS unit.

### Keep related units together

Avoid file duplication and facilate file location by gathering related units togeher.

```shell
\--	product-details
 	|-- product-details.mdl.js
 	|-- product-details.ctrl.js
 	|-- product-details.tpl.html
 	\-- product-details.scss
```


## Promises and the -ing form

Consider using promises instead of callbacks, AngularJS works very well with them.

When declaring a function that uses promises, define the name using the -ing form.

**Example:**

```javascript
function gettingUsers() {
	...
}
```



## Use one-time binding

AngularJS introduced in version 1.3, a feature called one-time binding. This feature provides a way to indicate that a binding is to be processed just one time and remain unchanged.

**Before:**
```html
	<title>{{title}}</title>
```

**After:**
```html
	<title>{{::title}}</title>
```

For more information about that features check this [link](http://blog.thoughtram.io/angularjs/2014/10/14/exploring-angular-1.3-one-time-bindings.html)

## Namespacing

When defining module names, use the namespace form defined below.

```javascript
angular.modular('appName.core.users.UserManager', ['ui-router']);
```

This will avoid name colisions for modules.

**Note:** Considering that AngularJs does not avoid naming colisions between units defined on separate modules. You will have to handle naming colisions.

