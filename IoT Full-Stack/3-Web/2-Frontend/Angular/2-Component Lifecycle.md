Every component has a lifecycle that defined by a series of events that occur throughout the life of the component.

When an event occurs, you can execute code of your own using lifecycle hooks.
Some of the lifecycle hooks occur only once, and others occur multiple times as data changes throughout the life of the component.

Lifecycle Hooks:
- Only once:
	- OnInit
	- AfterContentInit
	- AfterViewInit
	- OnDestroy
- Multiple times (When Input Data Changes)
	- OnChanges
	- OnCheck
	- AfterContentChecked
	- AfterViewChecked

The Order for the lifecycle hooks when Input changes is:
- OnChanges
- OnInit
- OnCheck
- AfterContentInit
- AfterContentChecked
- AfterViewInit
- AfterViewChecked
- OnDestroy

## Implement Lifecycle hook
1. import the lifecycle event
``` ts
import { Component, OnInit} from '@angular/core';
```
2. Implement it in your component class
``` ts
export class HomeCompnent implements OnInit {
	constructor() {}
	ngOnInit(): void {
		// add what you need to be executed at the momemnt of event
	}
}
```