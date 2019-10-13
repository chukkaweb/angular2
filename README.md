# angular2
# https://www.agiratech.com/top-10-angular-best-practices/
# https://malcoded.com/posts/improve-your-angular-codebase/
# https://stackoverflow.com/questions/36490926/how-to-cancel-a-httprequest-in-angular-2
# https://stackoverflow.com/questions/38008334/angular-rxjs-when-should-i-unsubscribe-from-subscription
# https://blog.angulartraining.com/how-to-automatically-unsubscribe-your-rxjs-observables-tutorial-2f98b0560298
# https://netbasal.com/when-to-unsubscribe-in-angular-d61c6b21bad3

# Int
# https://github.com/sudheerj/angular-interview-questions#what-is-angular-framework
Js int
https://www.edureka.co/blog/interview-questions/javascript-interview-questions/
Clean code
https://itnext.io/clean-code-checklist-in-angular-%EF%B8%8F-10d4db877f74

# Same route refresh
https://stackoverflow.com/questions/47813927/how-to-refresh-a-component-in-angular

Iframe binding


https://stackoverflow.com/questions/52382608/angular-6-iframe-binding

 <script async src="//www.instagram.com/embed.js" charset="utf-8"></script>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

After response
setTimeout(function() {
 (<any>window).twttr.widgets.load();
 (<any>window).instgrm.Embeds.process();
 }, 1000);

# Angular app performance
https://medium.com/@spp020/44-quick-tips-to-fine-tune-angular-performance-9f5768f5d945
Ng add 

# Dynamically color apply
https://www.sitepoint.com/community/t/angular-2-4-changing-the-background-color-of-a-panel-dynamically/274747

# Seo in angular
Adding SEO support to Angular 6 application
https://www.codementor.io/mbaljeetsingh/adding-seo-support-to-angular-6-application-njwstknw1
https://buffer.com/library/free-seo-tools

# Google analytics
https://codeburst.io/using-google-analytics-with-angular-25c93bffaa18

https://neilpatel.com/blog/google-index/

# Deploy local server
sudo npm install  http-server -g
Switch to folder →  http-server "folder name"

# Dual display laptop to desktop	
https://help.ubuntu.com/stable/ubuntu-help/display-dual-monitors.html

https://medium.com/@spp020/44-quick-tips-to-fine-tune-angular-performance-9f5768f5d945

# Workspace and project file structure
The package.json is organized into two groups of packages:
Dependencies are essential to running applications.
DevDependencies are only necessary to develop applications.
 
# Dependencies
The packages listed in the dependencies section of package.json are essential to running applications.
The dependencies section of package.json contains:
Angular packages: Angular core and optional modules; their package names begin @angular/.
Support packages: 3rd party libraries that must be present for Angular apps to run.
Polyfill packages: Polyfills plug gaps in a browser's JavaScript implementation.
To add a new dependency, use the ng add command.

# he Ahead-of-Time (AOT) compiler
The Angular Ahead-of-Time (AOT) compiler converts your Angular HTML and TypeScript code into efficient JavaScript code during the build phase before the browser downloads and runs that code. Compiling your application during the build process provides a faster rendering in the browser.
Just-in-Time (JIT), which compiles your app in the browser at runtime.
Ahead-of-Time (AOT), which compiles your app at build time.
JIT compilation is the default when you run the ng build (build only) or ng serve (build and serve locally) CLI commands:
ng build --aot
ng serve --aot
 # Why compile with AOT?
Faster rendering
Fewer asynchronous requests  3)Smaller Angular framework download size
There's no need to download the Angular compiler if the app is already compiled. The compiler is roughly half of Angular itself, so omitting it dramatically reduces the application payload.
Detect template errors earlier
The AOT compiler detects and reports template binding errors during the build step before users can see them.
Controlling app compilation
When you use the Angular AOT compiler, you can control your app compilation in two ways:
By providing template compiler options in the tsconfig.json file.
For more information, see Angular template compiler options.
By specifying Angular metadata.
 
# Working on router link navigation	

Using router.navigateByUrl is similar to changing the location bar directly–we are providing the “whole” new URL.

 Whereas router.navigate creates a new URL by applying an array of passed-in commands, a patch, to the current URL.

Navigate navigatebyurl
Navigate based on the provided url. This navigation is always absolute.

navigateByUrl() takes a string as a parameter. navigate() takes an array of URL segments.

# RouterLink is used to declare the path.
 Router-outlet used to render the route. or grap the particular component view	
Navigating Imperatively
Router.navigate and Router.navigateByUrl. Both methods return a promise that resolve to true if the navigation is successful, null if there’s no navigation
Router.navigateByUrl
wherever you need to navigate a user to another route, just inject the router and use navigateByUrl method:

Router.navigateByUrl is basically the same as Router.navigate, except that a string is passed-in instead of url segments and the navigation should be absolute and start with a /:

# 3. Lazy loading a feature module
const routes: Routes = [
 {
   path: 'dashboard',
   loadChildren: 'app/dashboard/dashboard.module#DashboardModule',
   component: CoreComponent
 }
];

# trackBy
When using ngFor to loop over an array in templates, use it with a trackBy function which will return an unique identifier for each item.

Why?
When an array changes, Angular re-renders the whole DOM tree. But if you use trackBy, Angular will know which element has changed and will only make DOM changes for that particular element.
# const vs let
When declaring variables, use const when the value is not going to be reassigned.
Why?
Using let and const where appropriate makes the intention of the declarations clearer. It will also help in identifying issues when a value is assigned to a constant accidentally by throwing a compile time error. It also helps improve the readability of the code.
 # Isolate API hacks
Not all APIs are bullet proof — sometimes we need to add some logic in the code to make up for bugs in the APIs. Instead of having the hacks in components where they are needed, it is better to isolate them in one place — like in a service and use the service from the component.
Why?
This helps keep the hacks “closer to the API”, so as close to where the network request is made as possible. This way, less of your code is dealing with the un-hacked code. Also, it is one place where all the hacks live and it is easier to find them. When fixing the bugs in the APIs, it is easier to look for them in one file rather than looking for the hacks that could be spread across the codebase.
You can also create custom tags like API_FIX similar to TODO and tag the fixes with it so it is easier to find.

# Clean up subscriptions
When subscribing to observables, always make sure you unsubscribe from them appropriately by using operators like take, takeUntil, etc.
Why?
Failing to unsubscribe from observables will lead to unwanted memory leaks as the observable stream is left open, potentially even after a component has been destroyed / the user has navigated to another page.
Even better, make a lint rule for detecting observables that are not unsubscribed.

# Avoid any; type everything;
Always declare variables or constants with a type other than any.
Why?
When declaring variables or constants in Typescript without a typing, the typing of the variable/constant will be deduced by the value that gets assigned to it. This will cause unintended problems. One classic example is:

before
const x = 1;
const y = 'a';
const z = x + y;
console.log(`Value of z is: ${z}`
// Output
Value of z is 1a

# Make use of lint rules
tslint has various options built in already like no-any, no-magic-numbers, no-console, etc that you can configure in your tslint.json to enforce certain rules in your code base.
Why?
Having lint rules in place means that you will get a nice error when you are doing something that you should not be. This will enforce consistency in your application and readability. Please refer here for more rules that you can configure.

// tslint.json
{
   "rules": {
       .......
       "no-console": [
            true,
            "log",    // no console.log allowed
            "warn"    // no console.warn allowed
       ]
  }
}

# Small reusable components

# Components should only deal with display logic
Avoid having any logic other than display logic in your component whenever you can and make the component deal only with the display logic.
Why?
Components are designed for presentational purposes and control what the view should do. Any business logic should be extracted into its own methods/services where appropriate, separating business logic from view logic.
Business logic is usually easier to unit test when extracted out to a service, and can be reused by any other components that need the same business logic applied.
 # Avoid long methods
Long methods generally indicate that they are doing too many things. Try to use the Single Responsibility Principle. The method itself as a whole might be doing one thing, but inside it, there are a few other operations that could be happening. We can extract those methods into their own method and make them do one thing each and use them instead.
Why?
Long methods are hard to read, understand and maintain. They are also prone to bugs, as changing one thing might affect a lot of other things in that method. They also make refactoring (which is a key thing in any application) difficult.
This is sometimes measured as “cyclomatic complexity”. There are also some TSLint rules to detect cyclomatic/cognitive complexity, which you could use in your project to avoid bugs and detect code smells and maintainability issues.

 # DRY
Do not Repeat Yourself. Make sure you do not have the same code copied into different places in the codebase. Extract the repeating code and use it in place of the repeated code.
Why?
Having the same code in multiple places means that if we want to make a change to the logic in that code, we have to do it in multiple places. This makes it difficult to maintain and also is prone to bugs where we could miss updating it in all occurrences. It takes longer to make changes to the logic and testing it is a lengthy process as well.
In those cases, extract the repeating code and use it instead. This means only one place to change and one thing to test. Having less duplicate code shipped to users means the application will be faster.

# Add caching mechanisms
When making API calls, responses from some of them do not change often. In those cases, you can add a caching mechanism and store the value from the API. When another request to the same API is made, check if there is a value for it in the cache and if so, use it. Otherwise, make the API call and cache the result.
If the values change but not frequently, you can introduce a cache time where you can check when it was last cached and decide whether or not to call the API.
Why?
Having a caching mechanism means avoiding unwanted API calls. By only making the API calls when required and avoiding duplication, the speed of the application improves as we do not have to wait for the network. It also means we do not download the same information over and over again.

# Strings should be safe
If you have a variable of type string that can have only a set of values, instead of declaring it as a string type, you can declare the list of possible values as the type.
Why?
By declaring the type of the variable appropriately, we can avoid bugs while writing the code during compile time rather than during runtime.
Before
private myStringValue: string;
if (itShouldHaveFirstValue) {
  myStringValue = 'First';
} else {
  myStringValue = 'Second'
}
After
private myStringValue: 'First' | 'Second';
if (itShouldHaveFirstValue) {
  myStringValue = 'First';
} else {
  myStringValue = 'Other'
}
// This will give the below error
Type '"Other"' is not assignable to type '"First" | "Second"'
(property) AppComponent.myValue: "First" | "Second"


# Jest
Jest is Facebook’s unit testing framework for JavaScript. It makes unit testing faster by parallelising test runs across the code base. With its watch mode, only the tests related to the changes made are run, which makes the feedback loop for testing way shorter. Jest also provides code coverage of the tests and is supported on VS Code and Webstorm.
You could use a preset for Jest that will do most of the heavy lifting for you when setting up Jest in your project.

File Naming

For example home.component.ts or home.component.html or auth.service.ts …

# Using Interfaces
If we want to create a contract for our class we should always use interfaces. By using them we can force the class to implement functions and properties declared inside the interface. Let’s take for example OnInit interface and its implementation:

# Constructor Usage
We should use the constructor method to setup Dependency Injection for our services and that is pretty much it. We shouldn’t be doing any work inside it, especially fetching the data from the server. For this type of actions, we have the lifecycle hooks in Angular.
Even though we can use the service injection inside the constructor:
private router: Router;
 
constructor(routerParam: Router) {
  this.router = routerParam;
}
# Safe Navigation Operator (?) in HTML Template
To be on the safe side we should always use the safe navigation operator while accessing a property from an object in a component’s template. If the object is null and we try to access a property, we are going to get an exception. But if we use the save navigation (?) operator, the template will ignore the null value and will access the property once the object is not the null anymore.
XHTML
1
2
3
<div class="col-md-3">
  {{user?.name}}
</div>

# Multi Modules in Application

# Shared module

# Using Lifecycle Hooks
Lifecycle hooks play a very important part of Angular development. We should use them whenever we have an opportunity to. For example, if we need to fetch some data from a database as soon as our component is instantiated, we should use ngOnInit() lifecycle hook and not the constructor.
If we have some logic inside child components and we want to execute that logic as soon as decorator parameters are modified, we can use ngOnChanges() lifecycle hook.
If we need to clean up some resources as soon as our component is destroyed, we should use ngOnDestroy() lifecycle hook.
Even though we don’t have to implement interfaces to use the lifecycle hooks, we are better off implementing them.
So don’t do something like this:
.export class OwnerListComponent {
 
  constructor() { }
 
  ngOnInit() {
    this.getAllOwners();
  }

# Use seed projects to hit the ground running!
Make use of some kickass starter seed projects because they would have done a great job at incorporating many features for you. I wholeheartedly 

# Small functions
 Using Visual Studio Code and installing ‘angular2-useful-dev-extensions’, ‘Angular v4 TypeScript Snippets’
# Some best practices from the Angular team
	Break everything into components. App module should be at the root of your application.
	Modularize your use case to make widgets. A widget contains an angular component, its template and style.
	Each component and template should not exceed 400 lines
	Make functions smaller. The maximum lines on a function should not exceed 10-15 lines (derived from Uncle Bob’s clean code)
	Use consistent name for all assets. Make classes upper camel case. Class name should be noun and method names should be verb.
	Append symbol name with conventional suffix. (for example, the login component can be named as LoginComponent with Component suffixed).
	File name should have conventional suffix. For example, a component can have its name suffixed with component.
	Use lower camel case for naming selectors and components.
	Separate words with hyphens in selectors.
	The best way to store bootstraping and platform information is main.ts.
	Configure your components to use logger. Use proper error handling.
	Unit testing is mandatory and the test spec file should have the same name as the component name.
	Do not use capital letters for constants. Use lower camel case instead.
	Do not use data type names while naming properties. ‘strusrename’ is wrong and ‘username’ is correct.
	Stop prefixing interfaces with ‘I’. It is a typescript best practice as some predefined interfaces use I during compilation.
	Use classes instead of interfaces. In ES5 and above only classes exist and even though we write interfaces, it will be converted into classes.
	Import line spacing. Leave an empty line between angular imports and custom imports
	Follow the LIFT principle (Locate your code quickly, Identify the code easily, Flattest structure, Try DRY. )
	Use lazy loading on subcomponents and where ever possible.

11 Angular Component Libraries You Should Know In 2019

https://blog.bitsrc.io/11-angular-component-libraries-you-should-know-in-2018-e9f9c9d544ff

# Server side rendering:
Rendering the first page of your application on the server (using Node.js, .Net, PHP) and serving it as a static page causes near to instant rendering thus greatly improves perceived performance, speed, and overall user experience. You can use Angular Universal to perform server side rendering.
# Updating Angular and angular-cli: 
Updating your Angular and angular-cli regularly gives you the benefit of many performance optimizations, bug fixes, new features, security etc.
 # Service worker cache: 
 If you have configured your app to support Progressive Web App, make sure to specify all the necessary static resources in the PWA config JSON. These static files will be cached in the client’s browser making the second time load much faster.
# Third party packages:
Review the third party packages you are using and see if better and smaller alternative is available as it may reduce the final size of your build.
# defer attribute:
Mentioning defer attribute to your script tag will defer the loading of the scripts (sychronous) until the document is not parsed thus making your site interactive quicker. For angular-cli app currently there is no way to add this automatically during the build, you have to do it manually after the build.
# async attribute: 
Just like the defer attribute, async delays the loading of scripts until the document is not parsed but without respecting the order of loading of the scripts. The best example to use it with google analytics script which usually independent of any other scripts.
# Updating Third Party Packages: 
Make sure you are regularly updating your third party packages
# Remove unused fonts: 
It’s a good idea to remove the unused fonts which may help you save few bytes over the network.


Navigate navigatebyurl
Navigate based on the provided url. This navigation is always absolute.

navigateByUrl() takes a string as a parameter. navigate() takes an array of URL segments.
# Each component and template should not exceed 400 lines

# Avoid code comments
// check if meal is healthy or not avoid
if (meal.calories < 1000 &&
   meal.hasVegetables) {
 ...
}

# Don’t use nested subscriptions
 Avoid complex computations in the template: Avoid doing complex calculation in the HTML template (ex calling some component method inside the template),
Slow DNS and SSL: Sometimes your DNS and SSL provider could be the reason for slow load time. So make sure the DNS and SSL are fast and configured correctly.

 console.log(): Using console.log() statements in your production code could be a bad idea as it will slow down the performance of the app and also logging objects with console.log() creates memory leak issue

# use strict'; 
export const sep='/'; export const version: string="22.2.2";
# State management (if necessary)
Consider using @ngrx/store for maintaining the state of your application and @ngrx/effects 
When building large, complex applications that has lots of information coming from and going to the database, and where state is shared across multiple components, you might start considering adding a state management library. By using a state management library, you are able to keep the application state in one single place, which reduces the communication between components and keeps your app more predictable and easier to understand.
# Shorten your relative paths
import { FooPipe } from '../../../../../shared/pipes/foo/foo.pipe'; wrong
import { FooPipe } from '@shared/pipes/foo/foo.pipe'; right
paths it should map by modifying our tsconfig.json
{
...
 "compilerOptions": {
   ...
   "baseUrl": "src",
   "paths": {
     "@env": ["environments/environment"],
     "@shared/*": ["app/shared/*"],
     "@core/*": ["app/core/*"]
   }
 }
}
 
# Use SCSS Variables 
Create a file src/styles/variables.scss and add your SCSS variables, extends, mixins, etc inside:
$accent: #0093ff;
 
Angular configuration file angular.json. Add the following after both of the "styles": ["src/styles.scss"] instances: 
angular.json
"stylePreprocessorOptions": {
 "includePaths": ["src/styles"]
},
 
// shared/components/button-a/button-a.component.scss
@import 'variables.scss';
button {
 background: $accent;
}
 
 





