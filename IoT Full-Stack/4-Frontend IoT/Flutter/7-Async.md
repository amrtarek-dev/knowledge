
Asynchronous programming

- API interactions are asynchronous network requests
- Response maybe unpredictable.
- Handling these blocking operations synchronously forces the app to wait for the API response before continuing which block the main thread (Causing the app to freeze or become unresponsive)

Solution:
Use **Future & async/await** keywords

- **Futures**: is a potential values or errors that aren't available yet.
	- A place holder for values of async operations
- **Async/await**: pauses code execution until the future value is returned

#### API call steps
1. Identify address or endpoint
2. Use http package to connect to server.
3. Interpret the response (JSON)
	1. json.decode to have Dart object (dart:convert)
4. Update the stateful widget to show the data.
	1. Using provider Riverpod, setState, or block
5. Implement handling errors
	1. Try-catch
	2. Timeouts
	3. User messages


> Implement debouncing request and caching response to minimize the number of API calls
> Use HTTPS
> Use modular logic 