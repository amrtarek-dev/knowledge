To display data in the component html, you can use:

- Interpolation
- Attribute Binding

Let's make a new data type in the type script, you can make a new file in the component directory called `product.model.ts`

``` ts
export interface IProduct {
	id: number;
	description: string;
	name: string;
	imageName: string;
	price: number;
	discount: number;
}
```


``` ts
import { IProduct } from './product.model'

export class CatalogComponent {
	product: IProduct;

	constructor() {
		this.product = {
		id: 1,
		description: "This is the product description",
		name: "This is the Product name",
		imageName: "product.png",
		price: 199,
		discount: 0.2,
		};
	}

	getImageUrl(product: IProduct) {
		return '/assets/image/products' + product.imageName;
	}
}
```

## Interpolation `{{ }}`
In the component html file

``` html
<div class="name">{{ product.name }}</div>
<div>$ {{ product.price.toFixed(2) }}</div>
<img src="{{ '/assets/image/robot-parts/' + product.imageName }}" alt="{{ product.name }}" />
```

## Attribuite Binding [ ]
in the component html you can use `[ arrtibute ]` to make angular interpolate the value

``` html
<img src="{{ '/assets/image/robot-parts/' + product.imageName }}" [alt]="product.name" />
```

