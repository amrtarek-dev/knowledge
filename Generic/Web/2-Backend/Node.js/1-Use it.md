
## 1. **Initialize a Project**
- Initialize the project with npm:
```bash
npm init -y
```
This will create a `package.json` file that stores metadata about your project, such as its name, version, and dependencies.

## 2. Install Packages (Dependencies)
For example, if you want to install: 
**Express.js**, a popular Node.js framework:

``` bash
npm install express
```

This will:
- Add Express to your `node_modules` folder (where dependencies are stored).
- Update the `package.json` file to include Express as a dependency.

| `npm install`            | `dependencies`    | Packages required for the app to work in production. |
| ------------------------ | ----------------- | ---------------------------------------------------- |
| `npm install --save-dev` | `devDependencies` | Packages needed only during development.             |
- **Use `npm install`** for:
	- Frameworks like `express`, `mongoose`, or `axios`.
	- Libraries or tools that the app relies on in production.
- **Use `npm install --save-dev`** for:
	- Development tools like `eslint`, `nodemon`, `webpack`, or `jest`
	- Testing frameworks, linters, and build scripts.

Here are some handy npm packages:
- **Express**: For creating servers and APIs.
- **dotenv**: For managing environment variables.
- **Mongoose**: For working with MongoDB databases.
- **Cors**: For enabling cross-origin requests.

## **3.Run App**

1. Create an `index.js` file:
``` bash
touch index.js
```

index.js:
``` javascript
const express = require('express');
const app = express();

app.get('/', (req, res) => {
    res.send('Hello, World!');
});

const PORT = 3000;
app.listen(PORT, () => {
    console.log(`Server is running on http://localhost:${PORT}`);
});
```

2. Run the app
``` bash
node index.js
```
Open your browser and go to `http://localhost:3000` to see "Hello, World!"

#### **Using npm Scripts**
You can define scripts in your `package.json`. For example:
``` json
"scripts": {
    "start": "node index.js"
}
```
Now you can start your app with:
``` bash
npm start
```