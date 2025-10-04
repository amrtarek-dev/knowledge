It is a way to dealing with asynchronous data, which is a way to do not pause your application waiting for the web server to do his work.
Normally Javascript deals with the asynchronous data by:
- `Callbacks` ( it has a lot of issues like the callback hell or pyramid of hell)
- `Promises` ( it allow the callback to fail in case of the error (builtin without try-catch), and it is composable you can put together several promises)
- `Observables` it is a bigger version of Promises


## subscribe

When you need to get data from the server, you might have code like this
``` ts
let userData = getUserDataFromServer(); // it can take a 1,2 sec to get the data.
```
So it could block the application until getting the data, so it is wise to make it observable by 
``` ts
let userDataObs = getUserDataObservable()
userDataObs.subscribe(userData => {
	// process data
})
```
The `userData` will have the data once it is ready, and it will not block the system to do so.

There is an alternative syntax for the callback rather than using only the `userData`
``` ts
let userDataObs = getUserDataObservable();
userDataObs.subscribe({
	next: userData => { /* process data */ },
	error: error => { /* handler error */ },
	complete: () => { /* handle complete (Not common to use) */}
});
```
Where `next` is the callback only when we pass the request, `error` is a callback when error occurred, and `complete` is a callback when the `next` callback done.


## pipe
the pipe method is a way to process the data before the subscribe function get the data, so it is wise to process the data with pipe especially if the data going to be used by multiple subscribers.

``` ts
let numberObs = from(4);

numberObs.pipe( map((num) => { return num +1 }); );
numberObs.subscribe(data); // 5
```

## Create Observables
We can make an Observables by using `BehaviorSubject`class
``` ts
let myNumber = new BehaviorSubject<number>();

myNumber.subscribe(num => {
	console.log(num)
});

myNumber.next(1);
```