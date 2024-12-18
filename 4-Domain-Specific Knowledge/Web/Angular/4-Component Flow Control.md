You can control the flow and make decision in the Angular front-end by using a special angular syntax called directive:

## Angular Directive
Angular directive like special HTML attributes that are only recognised by Angular.
There is a built-in directives like `ngClass`, `*ngIf`, `*ngFor`, and you can even make your custom directives.

### Structural directives *
Directives that change the structure of an HTML document by adding or removing HTML element, they have the `*` before the name of the directive. like `*ngIf`, ` *ngFor`


At beginning lets have a TypeScript file for a component like this:

``` ts
import { IProduct } from './product.model'

export class CatalogComponent {
	products: IProduct[];

	constructor() {
		this.products = [
		{
		id: 1,
		description: "This is the product description",
		name: "This is the Product name",
		imageName: "product.png",
		price: 199,
		discount: 0.2,
		}, 
		{
		id: 2,
		description: "This is the product description 2",
		name: "This is the Product name 2",
		imageName: "product2.png",
		price: 299,
		discount: 0.4,
		}, 
		];
	}

	getImageUrl(product: IProduct) {
		return '/assets/image/products' + product.imageName;
	}
}
```

#### `*ngFor`
To repeat a part of the code use the `*ngFor` as a javascript for loop

```html
<li class="product-item" *ngFor="let product of products">
	<div class="product-details">
		<div class="name"> {{ product.name }} </div>
	</div>
</li>
```

This will make a `product` variable from the `products` array and repeat the full html tag for every value in the array.

#### `*ngIf`

To show only if

``` html
<div class="price">
	<div *ngif="product.discount === 0"> ${{ product.price.toFixed(2)}}</div>
</div>
```

#### `*ngSwitch`