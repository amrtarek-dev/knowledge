
# HTML
HTML stands for HyperText Markup Language, it enables documents to be displayed as web pages on the Internet.
Tags represent the elements of an HTML page like paragraphs, lists and tables.

The HTML structure has the following components:
- The `<!DOCTYPE html>` defines that the page is a HTML5 document. This helps with standardisation across different browsers and tells the browser to use HTML5 to interpret the page.
- The `<html>` element is the root element of the HTML page - all other elements come after this element.
- The `<head>` element contains information about the page (such as the page title)
- The `<body>` element defines the HTML document's body; only content inside of the body is shown in the browser.
- The `<h1>` element defines a large heading
- The `<p>` element defines a paragraph
- There are many other elements (tags) used for different purposes. For example, there are tags for buttons (`<button>`), images (`<img>`), lists, and much more.   

Tags can contain attributes such as the class attribute which can be used to style an element (e.g. make the tag a different color) `<p class="bold-text">`, or the _src_ attribute which is used on images to specify the location of an image: `<img src="img/cat.jpg">.`An element can have multiple attributes each with its own unique purpose, e.g., <p attribute1="value1" attribute2="value2">.

Elements can also have an id attribute (`<p id="example">`), which is unique to the element. Unlike the class attribute, where multiple elements can use the same class, an element must have different id's to identify them uniquely. Element id's are used for styling and to identify it by JavaScript.

## HTML5
HTML5 is the latest version that supports:
- HTML or XML syntax
- Interoperation with earlier HTML versions
- Markup and APIs for idioms
- Managing data, video , and audio tools.
- Developing cross-browser and cross-platform applications
- Creating engaging user experience

### DOM (Document Object Model)
HTML DOM is an in-memory representation of a document:
- Contains nodes that define the document type and structure like:
	- Headers and paragraphs
	- Text nodes
	- Comment nodes