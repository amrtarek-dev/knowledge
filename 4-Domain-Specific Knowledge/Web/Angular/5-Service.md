Services in Angular is the packet that you have to add the logic to a component.

To create a service:
``` bash
ng generate service <service-name>
ng g s <service-name>
```

This command will create a service with file

``` ts
import { Injectable } from '@angular/core';

@Injectable({
	providedIn: 'root'
})
export class CartService {

	constructor() { }
}
```


> Services in Angular is singleton, so there is only one instance of the service among all the app.