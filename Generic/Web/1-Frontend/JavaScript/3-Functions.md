
There are 3 function expression in javascript:
- Function expression
- Multiline arrow function
- Single line arrow function

## Function expression
``` js
const isDavid = function (name) {
	return (name === "David");
}
```

## Multiline arrow function
``` js
const isDavid = (name) => {
	return (name === "David");
}

const logArray = (item, index) => {
	console.log(`${index}: ${item}`);
}
```

## Single line arrow function
``` js
const isDavid = (name) => name === "David";
```
Single line arrow function with no parameters
``` js
const lineBreak = () => console.log("")
```