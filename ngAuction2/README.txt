

Chapter 2: 

TO-DO


Chapter 3:

3.7.1. ProductService

injecting the ProductService into the HomeComponent

You’ll also implement the navigation so that when the user clicks the product title, the Router will render the ProductDetail component in the <router-outlet> area.

ProductService contains hardcoded data about products and the API to retrieve them.

Angular create an instance of the ProductService class and inject it into ProductItemComponent and ProductDetailComponent so they can invoke the getProducts() and getProductById() methods on the service.

3.7.2. ProductItemComponent

ProductItemComponent knows how to render one product based on the product provided by its parent (HomeComponent). 
its property product decorated with @Input()

you bind the product’s price, title, and id properties in the component’s template

Note that product.title is a routerLink that will navigate to ProductDetailComponent when the user clicks it

3.7.3. HomeComponent

HomeComponent - modify the constructor to inject the ProductService and retrieve the products in the ngOnInit() method.

Modify home.component.html to loop through the array products with the structural directive *ngFor and render each product.

he NgFor directive is used inside the component template to loop through the list of items in the data collection, rendering HTML markup for each item. 

3.7.4. StarsComponent

starts.component.ts

 Decorates the property count with @Input 
  so the parent component can assign its value using property binding

2 Decorates the property rating with @Input for the same reason

There are several popular libraries of icon fonts out there
Material Design Icons

The ProductItemComponent will be the parent of the StarsComponent.
<div class="ratings">                                     1
  <nga-stars [rating]="product.rating"></nga-stars>       2
 </div>

3.7.5. ProductDetailComponent

You want to add another route so that when the user clicks on the product title in the ProductItemComponent, the Router replaces HomeComponent with ProductDetailComponent. 
Configuring a route for the URL fragments, like products/123

The ProductDetailComponent will receive the selected product ID from the parent via the injected ActivatedRoute and then make a request to ProductService to retrieve product details.




