Components in Angular allows you to define html, css, javascript for a page or a section of page.

To make a component
``` bash
ng generate component <component-name>
ng g c <component-name>
```
This will make 2 things:
- Create 4 files
	- /src/app/components/component-name/
		- component-name.component.html
		- component-name.component.scss
		- component-name.component.specs.ts (unittest)
		- component-name.component.ts
- it will add the component to /src/app/app.module.ts
	- `import { HomeComponent } form './home/home.component`;
	- `@NgModule({ declarations: [ HomeComponent ] })`

component-name.component.ts file will be created which is for typescript code.

```ts
import { Component } from '@anguler/core';

@Component({
	selector: 'app-home',
	templateUrl: './home.component.html',
	styleUrls: ['./home.component.css']
})
export class HomeComponent {

}
```

the first line is importing the`component` from the angular/core library

then the decorator
@Component is a decorator from javascript concept to allow you to add a meta data to a class or other type of object.

This is how the angular knows that this class is component and allows you to specify the relevant data from that component.

## selector
selector is the tag that you can use to call the component in the HTML tag like 
```html
<app-home></app-home>
```
this will show the component in the specific html file
the first part of the tag is the prefix and you can change it in the `angular.json` file "prefix": "app"

## template & style
template and style are the ways that you can add HTML data and style to your component, 
you can use 
- `templateUrl` to add HTML code (page), or you can use the code it self if it is small with `template
- `styleUrls` to add style css to your component, or inline css style by using `styles`  

```ts
@Component({
selector: 'app-home'
template: `
	<p class="red">
		Inline howe works!
	</p>`,
styles:[`
	.red {
		color: red;
	}
	`]
})
```
> It is recommended to use the URL to have easier control for a big components. 

## Use the component
You can show the component by adding the selector tag to the app html file `/src/app/app.component.html`