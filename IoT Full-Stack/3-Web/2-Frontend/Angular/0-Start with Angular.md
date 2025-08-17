## Framework
A framework is a way to make the browsers host the full web app without getting back to the server for every view change, and it gives a capability to rerouting and split the app into components.

## Angular
Angular build primarily by using:
- Components
- Services
Components defined the user interface for a page or a part of a page, it has the HTML(Templates), CSS, and javascript (TypeScript) code.

Services only in typescript which has all the logic for a component.

## Angular Module
It is a container of components, directives, and services.

## JavaScript Vs TypeScript
- Static Typing
- Interfaces
- Class properties
- Public/private accessibility

### Static type
``` ts
let mystring: string = 'Hi';
let age: numner = 100;
let birthDate: date;
```

### Interface
``` ts
interface ICat {
 name: string;
 age?: numner;
}

let fluffy: ICat;

fluffy = {
 name: 'Fluffy',
 age: 7
}

fluffy = {
 name: 'Fluffy'
}

// you can make a variable optional by using ? symbol
```

### Class
```ts
class Cat {
 name: string;
 color: string;
 constructor (name) {
 this.name = name;
 }
}
```

### Public and Private Accessibility
By default and class member are public by default, to make it private

``` ts
class Cat {
 private name: string; // this will make it accessable only whithin the class
}
```
The common use is for initialise the class at the constructing moment

``` ts
class Cat {
 constructor(private name, private color) {
 }
}
// rather than

class Cat {
 private name: string;
 private color: string;
 constructor(name, color){
  this.name = name;
  this.color = color;
 }
}
```

## Development Environment

- Install an editor
	- vscode
- Install Node.js / NPM
	- Node version manager (nvm)
``` bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
```
once the nvm is installed
you can use
```bash
nvm install 18.10.0
nvm use 18.10.0
# or the latest lts
nvm install --lts
```
- Install Angular CLI
``` bash
npm install -g @angular/cli@16.0.0
```


## Angular project
make a new one by CLI
```bash
ng new <project-name>
```

to install npm dependances
```bash
cd to-the-project
npm install
```

to start npm server
```bash
npm start
```
this could be accessible on
localhost:4200

