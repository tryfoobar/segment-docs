---
title: 'Spec: V2 Ecommerce Events'
sidebar: 'Ecommerce'
redirect_from:
- '/advanced/spec/ecommerce/'
- '/advanced/spec/ecommerce/v2/'
---

Segment’s e-commerce spec helps define the journey for a customer as they browse your store, click on promotions, view products, add those products to a cart, and complete a purchase.

**Note:** Not all destinations support every event listed here. Please refer to individual destination docs for more information on supported events and properties.

## Event Lifecycles

Here is a list of supported events for our various categories within the customer journey.

### Browsing Overview

<span> </span>
<table>
  <tr>
    <th>**Action**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>Products Searched</td>
    <td>User searched for products</td>
  </tr>
  <tr>
    <td>Product List Viewed</td>
    <td>User viewed a product list or category</td>
  </tr>
  <tr>
    <td>Product List Filtered</td>
    <td>User filtered a product list or category</td>
  </tr>
</table>

### Promotions Overview

<span> </span>
<table>
  <tr>
    <th>**Action**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>Promotion Viewed</td>
    <td>User viewed promotion</td>
  </tr>
  <tr>
    <td>Promotion Clicked</td>
    <td>User clicked on promotion</td>
  </tr>
</table>

### Core Ordering Overview

<span> </span>
<table>
  <tr>
    <th>**Action**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>Product Clicked</td>
    <td>User clicked on a product</td>
  </tr>
  <tr>
    <td>Product Viewed</td>
    <td>User viewed a product details</td>
  </tr>
  <tr>
    <td>Product Added</td>
    <td>User added a product to their shopping cart</td>
  </tr>
  <tr>
    <td>Product Removed</td>
    <td>User removed a product from their shopping cart</td>
  </tr>
  <tr>
    <td>Cart Viewed</td>
    <td>User viewed their shopping cart</td>
  </tr>
  <tr>
    <td>Checkout Started</td>
    <td>User initiated the order process (a transaction is created)</td>
  </tr>
  <tr>
    <td>Checkout Step Viewed</td>
    <td>User viewed a checkout step</td>
  </tr>
  <tr>
    <td>Checkout Step Completed</td>
    <td>User completed a checkout step</td>
  </tr>
  <tr>
    <td>Payment Info Entered</td>
    <td>User added payment information</td>
  </tr>
  <tr>
    <td>Order Completed</td>
    <td>User completed the order</td>
  </tr>
  <tr>
    <td>Order Updated</td>
    <td>User updated the order</td>
  </tr>
  <tr>
    <td>Order Refunded</td>
    <td>User refunded the order</td>
  </tr>
  <tr>
    <td>Order Cancelled</td>
    <td>User cancelled the order</td>
  </tr>
</table>

### Coupons Overview
<span> </span>
<table>
  <tr>
    <th>**Action**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>Coupon Entered</td>
    <td>User entered a coupon on a shopping cart or order</td>
  </tr>
  <tr>
    <td>Coupon Applied</td>
    <td>Coupon was applied on a user’s shopping cart or order</td>
  </tr>
  <tr>
    <td>Coupon Denied</td>
    <td>Coupon was denied from a user’s shopping cart or order</td>
  </tr>
  <tr>
    <td>Coupon Removed</td>
    <td>User removed a coupon from a cart or order</td>
  </tr>
</table>

### Wishlisting Overview
<span> </span>
<table>
  <tr>
    <th>**Action**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>Product Added to Wishlist</td>
    <td>User added a product to the wish list</td>
  </tr>
  <tr>
    <td>Product Removed from Wishlist</td>
    <td>User removed a product from the wish list</td>
  </tr>
  <tr>
    <td>Wishlist Product Added to Cart</td>
    <td>User added a wishlist product to the cart</td>
  </tr>
</table>

### Sharing Overview
<span> </span>
<table>
  <tr>
    <th>**Action**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>Product Shared</td>
    <td>Shared a product with one or more friends</td>
  </tr>
  <tr>
    <td>Cart Shared</td>
    <td>Shared the cart with one or more friends</td>
  </tr>
</table>

### Reviewing Overview
<span> </span>
<table>
  <tr>
    <th>**Action**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>Product Reviewed</td>
    <td>User reviewed a product</td>
  </tr>
</table>

------------------------------------------------

The following section lists more detail for each lifecycle event as well as an example API call.

## Browsing

Browsing lifecycle events represent key events that a customer might have while browsing your apps.

### Products Searched

Fire this event when a visitor searches for products.

This event supports the following semantic properties:
<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>query</td>
    <td>String | Object</td>
    <td>Query the user searched with</td>
  </tr>
</table>

Example:
```js
analytics.track('Products Searched', {
  query: 'blue hotpants'
});
```

### Product List Viewed

Fire this event when a visitor views a product list or category.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>list_id</td>
    <td>String</td>
    <td>Product list being viewed</td>
  </tr>
  <tr>
    <td>category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>products</td>
    <td>Array<Product></td>
    <td>Products displayed in the product list</td>
  </tr>
  <tr>
    <td>products.$.product_id</td>
    <td>String</td>
    <td>Product id displayed on the list</td>
  </tr>
  <tr>
    <td>products.$.sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>products.$.name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>products.$.variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>products.$.price</td>
    <td>Number</td>
    <td>Price ($) of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.quantity</td>
    <td>Number</td>
    <td>Quantity of a product</td>
  </tr>
  <tr>
    <td>products.$.coupon</td>
    <td>String</td>
    <td>Coupon code associated with a product (e.g MAY_DEALS_3)</td>
  </tr>
  <tr>
    <td>products.$.position</td>
    <td>Number</td>
    <td>Position in the product list (ex. 3)</td>
  </tr>
  <tr>
    <td>products.$.url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>products.$.image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:
```
analytics.track('Product List Viewed', {
  list_id: 'hot_deals_1',
  category: 'Deals',
  products: [
    {
      product_id: '507f1f77bcf86cd799439011',
      sku: '45790-32',
      name: 'Monopoly: 3rd Edition',
      price: 19,
      position: 1,
      category: 'Games',
      url: 'https://www.example.com/product/path',
      image_url: 'https://www.example.com/product/path.jpg'
    },
    {
      product_id: '505bd76785ebb509fc183733',
      sku: '46493-32',
      name: 'Uno Card Game',
      price: 3,
      position: 2,
      category: 'Games'
    }
  ]
});
```

**Note:** the `Product List Viewed` event is aliased to the `Viewed Product Category` event (from e-commerce v1 spec).


### Product List Filtered

Fire this event when a visitor filters a product list or category.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>list_id</td>
    <td>String</td>
    <td>Product list being viewed</td>
  </tr>
  <tr>
    <td>category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>filters</td>
    <td>Array<Filter></td>
    <td>Product filters that the customer is using</td>
  </tr>
  <tr>
    <td>filters.$.type</td>
    <td>String</td>
    <td>Id of the filter type that the customer is using</td>
  </tr>
  <tr>
    <td>filters.$.value</td>
    <td>String</td>
    <td>Id of the selection that the customer chose</td>
  </tr>
  <tr>
    <td>sorts</td>
    <td>Array<Sort></td>
    <td>Product sorting that the customer is using</td>
  </tr>
  <tr>
    <td>sorts.$.type</td>
    <td>String</td>
    <td>Id of the sort type that the customer is using</td>
  </tr>
  <tr>
    <td>sorts.$.value</td>
    <td>String</td>
    <td>Id of the selection type the the customer is using (ascending, descending)</td>
  </tr>
  <tr>
    <td>products</td>
    <td>Array<Product></td>
    <td>Products displayed in the product list</td>
  </tr>
  <tr>
    <td>products.$.product_id</td>
    <td>String</td>
    <td>Product id displayed on the list</td>
  </tr>
  <tr>
    <td>products.$.sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>products.$.name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>products.$.variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>products.$.price</td>
    <td>Number</td>
    <td>Price ($) of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.quantity</td>
    <td>Number</td>
    <td>Quantity of a product</td>
  </tr>
  <tr>
    <td>products.$.coupon</td>
    <td>String</td>
    <td>Coupon code associated with a product (e.g MAY_DEALS_3)</td>
  </tr>
  <tr>
    <td>products.$.position</td>
    <td>Number</td>
    <td>Position in the product list (ex. 3)</td>
  </tr>
  <tr>
    <td>products.$.url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>products.$.image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:
```js

analytics.track('Product List Filtered', {
  list_id: 'todays_deals_may_11_2016',
  filters: [
    {
      type: 'department',
      value: 'beauty'
    },
    {
      type: 'price',
      value: 'under-$25'
    },
  ],
  sorts: [
    {
      type: 'price',
      value: 'desc'
    }
  ],
  products: [
    {
      product_id: '507f1f77bcf86cd798439011',
      sku: '45360-32',
      name: 'Dove Facial Powder',
      price: 12.60,
      position: 1,
      category: 'Beauty',
      url: 'https://www.example.com/product/path',
      image_url: 'https://www.example.com/product/path.jpg'
    },
    {
      product_id: '505bd76785ebb509fc283733',
      sku: '46573-32',
      name: 'Artin Hairbrush',
      price: 7.60,
      position: 2,
      category: 'Beauty'
    }
  ]
});
```

## Promotions

Promotion view/click events help you gather analytics on internal offers within your web or mobile app. For example, when a banner advertisement is shown in your web or app’s home page, you can fire a `Viewed Promotion`  event. If the user proceeds to click the advertisement, fire the `Clicked Promotion` event.

### Promotion Viewed

Fire this event when a user views a promotion.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
    <th>**Example**</th>
  </tr>
  <tr>
    <td>promotion_id</td>
    <td>String</td>
    <td>promotion’s ID</td>
    <td>promo_1</td>
  </tr>
  <tr>
    <td>creative</td>
    <td>String</td>
    <td>Promotion’s creative</td>
    <td>top_banner_2</td>
  </tr>
  <tr>
    <td>name</td>
    <td>String</td>
    <td>Promotion’s name</td>
    <td>75% store-wide shoe sale</td>
  </tr>
  <tr>
    <td>position</td>
    <td>String</td>
    <td>Promotion’s position</td>
    <td>home_banner_top</td>
  </tr>
</table>

Example:
```js
analytics.track('Promotion Viewed', {
  promotion_id: 'promo_1',
  creative: 'top_banner_2',
  name: '75% store-wide shoe sale',
  position: 'home_banner_top'
});
```

**Note:** the `Promotion Viewed` event is aliased to the [`Viewed Promotion` event](/docs/integrations/google-analytics/#measuring-promotions)


### Promotion Clicked

Fire this event when a visitor clicks an internal offer promotion.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
    <th>**Example**</th>
  </tr>
  <tr>
    <td>promotion_id</td>
    <td>String</td>
    <td>promotion’s ID</td>
    <td>promo_1</td>
  </tr>
  <tr>
    <td>creative</td>
    <td>String</td>
    <td>Promotion’s creative</td>
    <td>top_banner_2</td>
  </tr>
  <tr>
    <td>name</td>
    <td>String</td>
    <td>Promotion’s name</td>
    <td>75% store-wide shoe sale</td>
  </tr>
  <tr>
    <td>position</td>
    <td>String</td>
    <td>Promotion’s position</td>
    <td>home_banner_top</td>
  </tr>
</table>

Example:

```js
analytics.track('Promotion Clicked', {
  promotion_id: 'promo_1',
  creative: 'top_banner_2',
  name: '75% store-wide shoe sale',
  position: 'home_banner_top'
});
```

**Note:** the `Promotion Clicked` event is aliased to the [`Clicked Promotion` event](/docs/integrations/google-analytics/#measuring-promotions)

## Core Ordering

These events represent the customer journey in regards to product ordering.

### Product Clicked

Fire this event when a visitor clicks a product.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>product_id</td>
    <td>String</td>
    <td>Database id of the product being viewed</td>
  </tr>
  <tr>
    <td>sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>price</td>
    <td>Number</td>
    <td>Price of the product being viewed</td>
  </tr>
  <tr>
    <td>quantity</td>
    <td>Number</td>
    <td>Quantity of a product</td>
  </tr>
  <tr>
    <td>coupon</td>
    <td>String</td>
    <td>Coupon code associated with a product (e.g MAY_DEALS_3)</td>
  </tr>
   <tr>
    <td>position</td>
    <td>Number</td>
    <td>Position in the product list (ex. 3)</td>
  </tr>
  <tr>
    <td>url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:

```js
analytics.track('Product Clicked', {
  product_id: '507f1f77bcf86cd799439011',
  sku: 'G-32',
  category: 'Games',
  name: 'Monopoly: 3rd Edition',
  brand: 'Hasbro',
  variant: '200 pieces',
  price: 18.99,
  quantity: 1,
  coupon: 'MAYDEALS',
  position: 3,
  url: 'https://www.example.com/product/path',
  image_url: 'https://www.example.com/product/path.jpg'
});
```

**Note:**

- The `sku` and `product_id` do not have to be different. If they are different, typically the `product_id` is a database identifier, like `9714107479` and the `sku` is a public-facing identifier like `SEG-02`.

- The `Product Clicked` event is aliased to the `Clicked Product` event from [e-commerce v1 spec](/docs/spec/ecommerce/).

### Product Viewed

Fire this event when a visitor views a product. That view might happen on a page, screen, or preview modal.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>product_id</td>
    <td>String</td>
    <td>Database id of the product being viewed</td>
  </tr>
  <tr>
    <td>sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>price</td>
    <td>Number</td>
    <td>Price ($) of the product being viewed</td>
  </tr>
  <tr>
    <td>quantity</td>
    <td>Number</td>
    <td>Quantity of a product</td>
  </tr>
  <tr>
    <td>coupon</td>
    <td>String</td>
    <td>Coupon code associated with a product (e.g MAY_DEALS_3)</td>
  </tr>
  <tr>
    <td>currency</td>
    <td>String</td>
    <td>Currency of the transaction</td>
  </tr>
   <tr>
    <td>position</td>
    <td>Number</td>
    <td>Position in the product list (ex. 3)</td>
  </tr>
    <tr>
    <td>value</td>
    <td>Number</td>
    <td>Total value of the product after quantity</td>
  </tr>
  <tr>
    <td>url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:

```js
analytics.track('Product Viewed', {
  product_id: '507f1f77bcf86cd799439011',
  sku: 'G-32',
  category: 'Games',
  name: 'Monopoly: 3rd Edition',
  brand: 'Hasbro',
  variant: '200 pieces',
  price: 18.99,
  quantity: 1,
  coupon: 'MAYDEALS',
  currency: 'usd',
  position: 3,
  value: 18.99,
  url: 'https://www.example.com/product/path',
  image_url: 'https://www.example.com/product/path.jpg'
});
```

**Note:**

- The `sku` and `product_id` do not have to be different. If they are different, typically the `product_id` is a database identifier, like `9714107479` and the `sku` is a public-facing identifier like `SEG-02`.

- The `Product Viewed` event is aliased to the `Viewed Product` event from [e-commerce v1 spec](/docs/spec/ecommerce/).

### Product Added

Fire this event when a visitor adds a product to their shopping cart.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>cart_id</td>
    <td>String</td>
    <td>Cart ID to which the product was added to</td>
  </tr>
  <tr>
    <td>product_id</td>
    <td>String</td>
    <td>Database id of the product being viewed</td>
  </tr>
  <tr>
    <td>sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>price</td>
    <td>Number</td>
    <td>Price ($) of the product being viewed</td>
  </tr>
  <tr>
    <td>quantity</td>
    <td>Number</td>
    <td>Quantity of a product</td>
  </tr>
  <tr>
    <td>coupon</td>
    <td>String</td>
    <td>Coupon code associated with a product (e.g MAY_DEALS_3)</td>
  </tr>
  <tr>
    <td>position</td>
    <td>Number</td>
    <td>Position in the product list (ex. 3)</td>
  </tr>
  <tr>
    <td>url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:

```js
analytics.track('Product Added', {
  cart_id: 'skdjsidjsdkdj29j',
  product_id: '507f1f77bcf86cd799439011',
  sku: 'G-32',
  category: 'Games',
  name: 'Monopoly: 3rd Edition',
  brand: 'Hasbro',
  variant: '200 pieces',
  price: 18.99,
  quantity: 1,
  coupon: 'MAYDEALS',
  position: 3,
  url: 'https://www.example.com/product/path',
  image_url: 'https://www.example.com/product/path.jpg'
});
```

**Note:**
- The `sku` and `product_id` do not have to be different. If they are different, typically the `product_id` is a database identifier, like `9714107479` and the `sku` is a public-facing identifier like `SEG-02`.

- The `Product Added` event is aliased to the `Added Product` event from [e-commerce v1 spec](/docs/spec/ecommerce/).

### Product Removed

Fire this event when a visitor removes a product from their shopping cart.

This event supports the following semantic properties:
<table>
  <tr>
<th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>cart_id</td>
    <td>String</td>
    <td>Cart ID to which the product was removed from</td>
  </tr>
  <tr>
    <td>product_id</td>
    <td>String</td>
    <td>Database id of the product being viewed</td>
  </tr>
  <tr>
    <td>sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>price</td>
    <td>Number</td>
    <td>Price ($) of the product being viewed</td>
  </tr>
  <tr>
    <td>quantity</td>
    <td>Number</td>
    <td>Quantity of a product</td>
  </tr>
  <tr>
    <td>coupon</td>
    <td>String</td>
    <td>Coupon code associated with a product (e.g MAY_DEALS_3)</td>
  </tr>
  <tr>
    <td>position</td>
    <td>Number</td>
    <td>Position in the product list (ex. 3)</td>
  </tr>
  <tr>
    <td>url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:
```js
analytics.track('Product Removed', {
  cart_id: 'ksjdj92dj29dj92d2j',
  product_id: '507f1f77bcf86cd799439011',
  sku: 'G-32',
  category: 'Games',
  name: 'Monopoly: 3rd Edition',
  brand: 'Hasbro',
  variant: '200 pieces',
  price: 18.99,
  quantity: 1,
  coupon: 'MAYDEALS',
  position: 3,
  url: 'https://www.example.com/product/path',
  image_url: 'https://www.example.com/product/path.jpg'
});
```

**Note:**

- The `sku` and `product_id` do not have to be different. If they are different, typically the `product_id` is a database identifier, like `9714107479` and the `sku` is a public-facing identifier like `SEG-02`.

- The `Product Removed` event is aliased to the `Removed Product` event from [e-commerce v1 spec](/docs/spec/ecommerce/#added-removed-product).

### Cart Viewed

Fire this event when a visitor views a shopping cart.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>cart_id</td>
    <td>String</td>
    <td>Shopping cart ID</td>
  </tr>
  <tr>
    <td>products</td>
    <td>Array<Product></td>
    <td>Products displayed in the product list</td>
  </tr>
  <tr>
    <td>products.$.product_id</td>
    <td>String</td>
    <td>Product ID displayed on the list</td>
  </tr>
  <tr>
    <td>products.$.sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>products.$.name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>products.$.variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>products.$.price</td>
    <td>Number</td>
    <td>Price ($) of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.quantity</td>
    <td>Number</td>
    <td>Quantity of a product</td>
  </tr>
  <tr>
    <td>products.$.coupon</td>
    <td>String</td>
    <td>Coupon code associated with a product (e.g MAY_DEALS_3)</td>
  </tr>
  <tr>
    <td>products.$.position</td>
    <td>Number</td>
    <td>Position in the product list (ex. 3)</td>
  </tr>
  <tr>
    <td>products.$.url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>products.$.image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:
```js
analytics.track('Cart Viewed', {
  cart_id: 'd92jd29jd92jd29j92d92jd',
  products: [
    {
      product_id: '507f1f77bcf86cd799439011',
      sku: '45790-32',
      name: 'Monopoly: 3rd Edition',
      price: 19,
      position: 1,
      category: 'Games',
      url: 'https://www.example.com/product/path',
      image_url: 'https://www.example.com/product/path.jpg'
    },
    {
      product_id: '505bd76785ebb509fc183733',
      sku: '46493-32',
      name: 'Uno Card Game',
      price: 3,
      position: 2,
      category: 'Games'
    }
  ]
});
```

### Checkout Started

Fire this event whenever an order/transaction was started. Fire on the page that the customer lands on after they press the checkout button.

Be sure to **include all items in the cart as event properties**, with the same properties from the previous calls, like so:

This event supports the following semantic properties:
<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>order_id</td>
    <td>String</td>
    <td>Order/transaction ID</td>
  </tr>
  <tr>
    <td>affiliation</td>
    <td>String</td>
    <td>Store or affiliation from which this transaction occurred (e.g. Google Store)</td>
  </tr>
  <tr>
    <td>value</td>
    <td>Number</td>
    <td>Revenue ($) with discounts and coupons added in. For better flexibility and total control over tracking, we let you decide how to calculate how coupons and discounts are applied</td>
  </tr>
  <tr>
    <td>revenue</td>
    <td>Number</td>
    <td>Revenue ($) associated with the transaction (excluding shipping and tax)</td>
  </tr>
  <tr>
    <td>shipping</td>
    <td>Number</td>
    <td>Shipping cost associated with the transaction</td>
  </tr>
  <tr>
    <td>tax</td>
    <td>Number</td>
    <td>Total tax associated with the transaction</td>
  </tr>
  <tr>
    <td>discount</td>
    <td>Number</td>
    <td>Total discount associated with the transaction</td>
  </tr>
  <tr>
    <td>coupon</td>
    <td>String</td>
    <td>Transaction coupon redeemed with the transaction</td>
  </tr>
  <tr>
    <td>currency</td>
    <td>String</td>
    <td>[Currency code](https://support.google.com/analytics/answer/6205902#supported-currencies) associated with the transaction</td>
  </tr>
  <tr>
    <td>products</td>
    <td>Array<Product></td>
    <td>Products in the order</td>
  </tr>
  <tr>
    <td>products.$.product_id</td>
    <td>String</td>
    <td>Database id of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>products.$.name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>products.$.variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>products.$.price</td>
    <td>Number</td>
    <td>Price ($) of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.quantity</td>
    <td>Number</td>
    <td>Quantity of a product</td>
  </tr>
  <tr>
    <td>products.$.coupon</td>
    <td>String</td>
    <td>Coupon code associated with a product (e.g MAY_DEALS_3)</td>
  </tr>
  <tr>
    <td>products.$.position</td>
    <td>Number</td>
    <td>Position in the product list (ex. 3)</td>
  </tr>
  <tr>
    <td>products.$.url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>products.$.image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:
```js
analytics.track('Checkout Started', {
  order_id: '50314b8e9bcf000000000000',
  affiliation: 'Google Store',
  value: 30,
  revenue: 25.00,
  shipping: 3,
  tax: 2,
  discount: 2.5,
  coupon: 'hasbros',
  currency: 'USD',
  products: [
    {
      product_id: '507f1f77bcf86cd799439011',
      sku: '45790-32',
      name: 'Monopoly: 3rd Edition',
      price: 19,
      quantity: 1,
      category: 'Games',
      url: 'https://www.example.com/product/path',
      image_url: 'https://www.example.com/product/path.jpg'
    },
    {
      product_id: '505bd76785ebb509fc183733',
      sku: '46493-32',
      name: 'Uno Card Game',
      price: 3,
      quantity: 2,
      category: 'Games'
    }
  ]
});
```

**Note:**

- The `sku` and `product_id` do not have to be different. If they are different, typically the `product_id` is a database identifier, like `9714107479` and the `sku` is a public-facing identifier like `SEG-02`.

- The `Checkout Started` event is aliased to the `Started Order` event from [Segment's GA Enhanced E-Commerce destinations](/docs/integrations/google-analytics/#measuring-checkout-steps).

### Checkout Step Viewed

Fire this event whenever a checkout step is viewed.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>checkout_id</td>
    <td>String</td>
    <td>Checkout transaction ID</td>
  </tr>
  <tr>
    <td>step</td>
    <td>Number</td>
    <td>Number representing a step in the checkout process</td>
  </tr>
  <tr>
    <td>shipping_method</td>
    <td>String</td>
    <td>String representing the shipping the method chosen</td>
  </tr>
  <tr>
    <td>payment_method</td>
    <td>String</td>
    <td>String representing the payment method chosen</td>
  </tr>
</table>

Example:
```js
analytics.track('Checkout Step Viewed', {
  checkout_id: '50314b8e9bcf000000000000',
  step: 2,
  shipping_method: 'Fedex',
  payment_method: 'Visa'
});
```

**Note:** `shipping_method` and `payment_method` are semantic properties so if you want to send that information, please do so in this exact spelling!

You can have as many or as few steps in the checkout funnel as you’d like. Note that you’ll still need to track the `Order Completed` event per our standard [e-commerce tracking API](/docs/spec/ecommerce/v2/#order-completed/) after you’ve tracked the checkout steps.

**Note:** The `Checkout Step Viewed` event is aliased to the `Viewed Checkout Step` event from [Segment's GA Enhanced E-Commerce destinations](/docs/integrations/google-analytics/#measuring-checkout-steps).

### Checkout Step Completed

Fire this event whenever a checkout step is completed.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>checkout_id</td>
    <td>String</td>
    <td>Checkout transaction ID</td>
  </tr>
  <tr>
    <td>step</td>
    <td>Number</td>
    <td>Number representing a step in the checkout process</td>
  </tr>
  <tr>
    <td>shipping_method</td>
    <td>String</td>
    <td>String representing the shipping the method chosen</td>
  </tr>
  <tr>
    <td>payment_method</td>
    <td>String</td>
    <td>String representing the payment method chosen</td>
  </tr>
</table>

Example:

```js
analytics.track('Checkout Step Completed', {
  checkout_id: '50314b8e9bcf000000000000',
  step: 2,
  shipping_method: 'Fedex',
  payment_method: 'Visa'
});
```

**Note:** `shipping_method` and `payment_method` are semantic properties so if you want to send that information, please do so in this exact spelling!

You can have as many or as few steps in the checkout funnel as you’d like. Note that you’ll still need to track the `Order Completed` event per our standard [e-commerce tracking API](/docs/spec/ecommerce/v2/#order-completed) after you’ve tracked the checkout steps.

**Note:** The `Checkout Step Completed` event is aliased to the `Completed Checkout Step` event from [Segment's GA Enhanced E-Commerce destinations](/docs/integrations/google-analytics/#measuring-checkout-steps).


### Payment Info Entered

Fire this event whenever payment information has been successfully entered.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>checkout_id</td>
    <td>String</td>
    <td>Checkout transaction ID</td>
  </tr>
  <tr>
    <td>order_id</td>
    <td>String</td>
    <td>Order ID (optional)</td>
  </tr>
  <tr>
    <td>step</td>
    <td>Number</td>
    <td>Number representing a step in the checkout process</td>
  </tr>
  <tr>
    <td>shipping_method</td>
    <td>String</td>
    <td>String representing the shipping the method chosen</td>
  </tr>
  <tr>
    <td>payment_method</td>
    <td>String</td>
    <td>String representing the payment method chosen</td>
  </tr>
</table>

Example:

```js
analytics.track('Payment Info Entered', {
  checkout_id: '39f39fj39f3jf93fj9fj39fj3f',
  order_id: 'dkfsjidfjsdifsdfksdjfkdsfjsdfkdsf'
});
```

**Note:** `shipping_method` and `payment_method` are semantic properties so if you want to send that information, please do so in this exact spelling!

You can have as many or as few steps in the checkout funnel as you’d like. Note that you’ll still need to track the `Completed Order` event per our standard [e-commerce tracking API](/docs/spec/ecommerce/v2/#order-completed) after you’ve tracked the checkout steps.

### Order Updated

Fire this event whenever an order/transaction was updated.

Be sure to **include all items in the cart as event properties**, with the same properties from the previous calls, like so:

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>order_id</td>
    <td>String</td>
    <td>Order/transaction ID</td>
  </tr>
  <tr>
    <td>affiliation</td>
    <td>String</td>
    <td>Store or affiliation from which this transaction occurred (e.g. Google Store)</td>
  </tr>
  <tr>
    <td>total</td>
    <td>Number</td>
    <td>Revenue ($) with discounts and coupons added in
      <p>Note that our Google Analytics Ecommerce destination accepts `total` *or* `revenue`, but not both. For better flexibility and total control over tracking, we let you decide how to calculate how coupons and discounts are applied</p></td>
  </tr>
  <tr>
    <td>revenue</td>
    <td>Number</td>
    <td>Revenue ($) associated with the transaction (excluding shipping and tax)</td>
  </tr>
  <tr>
    <td>shipping</td>
    <td>Number</td>
    <td>Shipping cost associated with the transaction</td>
  </tr>
  <tr>
    <td>tax</td>
    <td>Number</td>
    <td>Total tax associated with the transaction</td>
  </tr>
  <tr>
    <td>discount</td>
    <td>Number</td>
    <td>Total discount associated with the transaction</td>
  </tr>
  <tr>
    <td>coupon</td>
    <td>String</td>
    <td>Transaction coupon redeemed with the transaction</td>
  </tr>
  <tr>
    <td>currency</td>
    <td>String</td>
    <td>[Currency code](https://support.google.com/analytics/answer/6205902#supported-currencies) associated with the transaction</td>
  </tr>
  <tr>
    <td>products</td>
    <td>Array<Product></td>
    <td>Products in the order</td>
  </tr>
  <tr>
    <td>products.$.product_id</td>
    <td>String</td>
    <td>Database id of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>products.$.name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>products.$.variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>products.$.price</td>
    <td>Number</td>
    <td>Price ($) of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.quantity</td>
    <td>Number</td>
    <td>Quantity of a product</td>
  </tr>
  <tr>
    <td>products.$.coupon</td>
    <td>String</td>
    <td>Coupon code associated with a product (e.g MAY_DEALS_3)</td>
  </tr>
  <tr>
    <td>products.$.position</td>
    <td>Number</td>
    <td>Position in the product list (ex. 3)</td>
  </tr>
  <tr>
    <td>products.$.url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>products.$.image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:
```js
analytics.track('Order Updated', {
      order_id: '50314b8e9bcf000000000000',
      affiliation: 'Google Store',
      total: 27.50,
      revenue: 25.00,
      shipping: 3,
      tax: 2,
      discount: 2.5,
      coupon: 'hasbros',
      currency: 'USD',
      products: [
        {
          product_id: '507f1f77bcf86cd799439011',
          sku: '45790-32',
          name: 'Monopoly: 3rd Edition',
          price: 19,
          quantity: 1,
          category: 'Games',
          url: 'https://www.example.com/product/path',
  image_url: 'https://www.example.com/product/path.jpg'
        },
        {
          product_id: '505bd76785ebb509fc183733',
          sku: '46493-32',
          name: 'Uno Card Game',
          price: 3,
          quantity: 2,
          category: 'Games'
        }
      ]
    });
```

**Note:**
The `sku` and `product_id` do not have to be different. If they are different, typically the `product_id` is a database identifier, like `9714107479` and the `sku` is a public-facing identifier like `SEG-02`.

- The `Order Updated` event is aliased to the `Updated Order` event from [Segment's GA Enhanced E-Commerce destinations](/docs/integrations/google-analytics/#measuring-checkout-steps).


### Order Completed

Fire this event whenever an order/transaction was successfully completed by the customer.

Be sure to **include all items in the cart as event properties**, with the same properties from the previous calls, like so:

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>checkout_id</td>
    <td>String</td>
    <td>Checkout ID</td>
  </tr>
  <tr>
    <td>order_id</td>
    <td>String</td>
    <td>Order/transaction ID</td>
  </tr>
  <tr>
    <td>affiliation</td>
    <td>String</td>
    <td>Store or affiliation from which this transaction occurred (e.g. Google Store)</td>
  </tr>
  <tr>
    <td>total</td>
    <td>Number</td>
    <td>Revenue ($) with discounts and coupons added in. Note that our Google Analytics Ecommerce destination accepts `total` *or* `revenue`, but not both. For better flexibility and total control over tracking, we let you decide how to calculate how coupons and discounts are applied</td>
  </tr>
  <tr>
    <td>revenue</td>
    <td>Number</td>
    <td>Revenue ($) associated with the transaction (excluding shipping and tax)</td>
  </tr>
  <tr>
    <td>shipping</td>
    <td>Number</td>
    <td>Shipping cost associated with the transaction</td>
  </tr>
  <tr>
    <td>tax</td>
    <td>Number</td>
    <td>Total tax associated with the transaction</td>
  </tr>
  <tr>
    <td>discount</td>
    <td>Number</td>
    <td>Total discount associated with the transaction</td>
  </tr>
  <tr>
    <td>coupon</td>
    <td>String</td>
    <td>Transaction coupon redeemed with the transaction</td>
  </tr>
  <tr>
    <td>currency</td>
    <td>String</td>
    <td>[Currency code](https://support.google.com/analytics/answer/6205902#supported-currencies) associated with the transaction</td>
  </tr>
  <tr>
    <td>products</td>
    <td>Array<Product></td>
    <td>Products in the order</td>
  </tr>
  <tr>
    <td>products.$.product_id</td>
    <td>String</td>
    <td>Database id of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>products.$.name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>products.$.variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>products.$.price</td>
    <td>Number</td>
    <td>Price ($) of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.quantity</td>
    <td>Number</td>
    <td>Quantity of a product</td>
  </tr>
  <tr>
    <td>products.$.coupon</td>
    <td>String</td>
    <td>Coupon code associated with a product (e.g MAY_DEALS_3)</td>
  </tr>
  <tr>
    <td>products.$.position</td>
    <td>Number</td>
    <td>Position in the product list (ex. 3)</td>
  </tr>
  <tr>
    <td>products.$.url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>products.$.image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:

```js
analytics.track('Order Completed', {
  checkout_id: 'fksdjfsdjfisjf9sdfjsd9f',
  order_id: '50314b8e9bcf000000000000',
  affiliation: 'Google Store',
  total: 27.50,
  revenue: 25.00,
  shipping: 3,
  tax: 2,
  discount: 2.5,
  coupon: 'hasbros',
  currency: 'USD',
  products: [
    {
      product_id: '507f1f77bcf86cd799439011',
      sku: '45790-32',
      name: 'Monopoly: 3rd Edition',
      price: 19,
      quantity: 1,
      category: 'Games',
      url: 'https://www.example.com/product/path',
      image_url: 'https:///www.example.com/product/path.jpg'
    },
    {
      product_id: '505bd76785ebb509fc183733',
      sku: '46493-32',
      name: 'Uno Card Game',
      price: 3,
      quantity: 2,
      category: 'Games'
    }
  ]
});
```

**Note:**

- The `sku` and `product_id` do not have to be different. If they are different, typically the `product_id` is a database identifier, like `9714107479` and the `sku` is a public-facing identifier like `SEG-02`.

- The `Order Completed` event is aliased to the `Completed Order` event from [E-Commerce spec v1 - 5/11/16](/docs/spec/ecommerce/).

### Order Refunded

Fire this event whenever an order/transaction was refunded.

Be sure to **include all items in the cart as event properties**, with the same properties from the previous "Order Completed" call.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>order_id</td>
    <td>String</td>
    <td>Order/transaction ID</td>
  </tr>
</table>

Example:
```js
analytics.track('Order Refunded', {
  order_id: '50314b8e9bcf000000000000',
  total: 30,
  currency: 'USD',
  products: [
    {
      product_id: '507f1f77bcf86cd799439011',
      sku: '45790-32',
      name: 'Monopoly: 3rd Edition',
      price: 19,
      quantity: 1,
      category: 'Games',
      url: 'https://www.example.com/product/path',
      image_url: 'https://www.example.com/product/path.jpg'
    },
    {
      product_id: '505bd76785ebb509fc183733',
      sku: '46493-32',
      name: 'Uno Card Game',
      price: 3,
      quantity: 2,
      category: 'Games'
    }
  ]
});
```

**Note:** The `sku` and `product_id` do not have to be different. If they are different, typically the `product_id` is a database identifier, like `9714107479` and the `sku` is a public-facing identifier like `SEG-02`.


### Order Cancelled

Fire this event whenever an order/transaction was cancelled.

Be sure to **include all items in the cart as event properties**, with the same properties from the previous calls.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>order_id</td>
    <td>String</td>
    <td>Order/transaction ID</td>
  </tr>
  <tr>
    <td>affiliation</td>
    <td>String</td>
    <td>Store or affiliation from which this transaction occurred (e.g. Google Store)</td>
  </tr>
  <tr>
    <td>total</td>
    <td>Number</td>
    <td>Revenue ($) with discounts and coupons added in.</td>
  </tr>
  <tr>
    <td>revenue</td>
    <td>Number</td>
    <td>Revenue ($) associated with the transaction (excluding shipping and tax)</td>
  </tr>
  <tr>
    <td>shipping</td>
    <td>Number</td>
    <td>Shipping cost associated with the transaction</td>
  </tr>
  <tr>
    <td>tax</td>
    <td>Number</td>
    <td>Total tax associated with the transaction</td>
  </tr>
  <tr>
    <td>discount</td>
    <td>Number</td>
    <td>Total discount associated with the transaction</td>
  </tr>
  <tr>
    <td>coupon</td>
    <td>String</td>
    <td>Transaction coupon redeemed with the transaction</td>
  </tr>
  <tr>
    <td>currency</td>
    <td>String</td>
    <td>[Currency code](https://support.google.com/analytics/answer/6205902#supported-currencies) associated with the transaction</td>
  </tr>
  <tr>
    <td>products</td>
    <td>Array<Product></td>
    <td>Products in the order</td>
  </tr>
  <tr>
    <td>products.$.product_id</td>
    <td>String</td>
    <td>Database id of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>products.$.name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>products.$.variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>products.$.price</td>
    <td>Number</td>
    <td>Price ($) of the product being viewed</td>
  </tr>
  <tr>
    <td>products.$.quantity</td>
    <td>Number</td>
    <td>Quantity of a product</td>
  </tr>
  <tr>
    <td>products.$.coupon</td>
    <td>String</td>
    <td>Coupon code associated with a product (e.g MAY_DEALS_3)</td>
  </tr>
  <tr>
    <td>products.$.position</td>
    <td>Number</td>
    <td>Position in the product list (ex. 3)</td>
  </tr>
  <tr>
    <td>products.$.url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>products.$.image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:

```js
analytics.track('Order Cancelled', {
  order_id: '50314b8e9bcf000000000000',
  affiliation: 'Google Store',
  total: 30,
  revenue: 25.00,
  shipping: 3,
  tax: 2,
  discount: 2.5,
  coupon: 'hasbros',
  currency: 'USD',
  products: [
    {
      product_id: '507f1f77bcf86cd799439011',
      sku: '45790-32',
      name: 'Monopoly: 3rd Edition',
      price: 19,
      quantity: 1,
      category: 'Games',
      url: 'https://www.example.com/product/path',
      image_url: 'https://www.example.com/product/path.jpg'
    },
    {
      product_id: '505bd76785ebb509fc183733',
      sku: '46493-32',
      name: 'Uno Card Game',
      price: 3,
      quantity: 2,
      category: 'Games'
    }
  ]
});
```

**Note:** The `sku` and `product_id` do not have to be different. If they are different, typically the `product_id` is a database identifier, like `9714107479` and the `sku` is a public-facing identifier like `SEG-02`.

## Coupons

These are events that might occur when dealing with coupons in your ecommerce.

### Coupon Entered

Fire this event whenever a coupon is entered either on a cart or on an order/transaction.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>order_id</td>
    <td>String</td>
    <td>Order/transaction ID, if applicable</td>
  </tr>
  <tr>
    <td>cart_id</td>
    <td>String</td>
    <td>Cart ID, if applicable</td>
  </tr>
  <tr>
    <td>coupon_id</td>
    <td>String</td>
    <td>Coupon ID</td>
  </tr>
</table>

Example:

```js
analytics.track('Coupon Entered', {
      order_id: '50314b8e9bcf000000000000',
      cart_id: '923923929jd29jd92dj9j93fj3',
      coupon_id: 'may_deals_2016'
    });
```

**Note:** This should have no effect in GA enhanced e-commerce, as that destination should pull from the `coupon` field on the order events. Please refer to our [GA docs](/docs/integrations/google-analytics/) for more information.

### Coupon Applied

Fire this event whenever a coupon is successfully applied to either a cart or an order/transaction.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>order_id</td>
    <td>String</td>
    <td>Order/transaction ID, if applicable</td>
  </tr>
  <tr>
    <td>cart_id</td>
    <td>String</td>
    <td>Cart ID, if applicable</td>
  </tr>
  <tr>
    <td>coupon_id</td>
    <td>String</td>
    <td>Coupon ID</td>
  </tr>
  <tr>
    <td>coupon_name</td>
    <td>String</td>
    <td>Coupon name</td>
  </tr>
  <tr>
    <td>discount</td>
    <td>Number</td>
    <td>Monetary discount applied through the coupon</td>
  </tr>
</table>

Example:
```js
analytics.track('Coupon Applied', {
      order_id: '50314b8e9bcf000000000000',
      cart_id: '923923929jd29jd92dj9j93fj3'
      coupon_id: 'may_deals_2016',
      coupon_name: 'May Deals 2016',
      discount: 23.32
    });
```

**Note:** This should have no effect in GA enhanced e-commerce, as that destination should pull from the `coupon` field on the order events. Please refer to our [GA docs](/docs/integrations/google-analytics/) for more information.

### Coupon Denied

Fire this event whenever a coupon is denied from either a cart or an order/transaction.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>order_id</td>
    <td>String</td>
    <td>Order/transaction ID, if applicable</td>
  </tr>
  <tr>
    <td>cart_id</td>
    <td>String</td>
    <td>Cart ID, if applicable</td>
  </tr>
  <tr>
    <td>coupon_id</td>
    <td>String</td>
    <td>Coupon ID</td>
  </tr>
  <tr>
    <td>coupon_name</td>
    <td>String</td>
    <td>Coupon name</td>
  </tr>
  <tr>
    <td>reason</td>
    <td>String</td>
    <td>Reason the coupon was denied</td>
  </tr>
</table>

Example:

```js
analytics.track('Coupon Denied', {
      order_id: '50314b8e9bcf000000000000',
      cart_id: '923923929jd29jd92dj9j93fj3'
      coupon: 'may_deals_2016',
      reason: 'Coupon expired'
    });
```

**Note:** This should have no effect in GA enhanced e-commerce, as that destination should pull from the `coupon` field on the order events. Please refer to our [GA docs](/docs/integrations/google-analytics/) for more information.

### Coupon Removed

Fire this event whenever a coupon is removed from either a cart or an order/transaction.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>order_id</td>
    <td>String</td>
    <td>Order/transaction ID, if applicable</td>
  </tr>
  <tr>
    <td>cart_id</td>
    <td>String</td>
    <td>Cart ID, if applicable</td>
  </tr>
  <tr>
    <td>coupon_id</td>
    <td>String</td>
    <td>Coupon ID</td>
  </tr>
  <tr>
    <td>coupon_name</td>
    <td>String</td>
    <td>Coupon name</td>
  </tr>
  <tr>
    <td>discount</td>
    <td>Number</td>
    <td>Monetary discount applied through the coupon</td>
  </tr>
</table>

Example:
```js
analytics.track('Coupon Removed', {
  order_id: '50314b8e9bcf000000000000',
  cart_id: '923923929jd29jd92dj9j93fj3'
  coupon_id: 'may_deals_2016',
  coupon_name: 'May Deals 2016',
  discount: 23.32
});
```

**Note:** This should have no effect in GA enhanced e-commerce, as that destination should pull from the `coupon` field on the order events. Please refer to our [GA docs](/docs/integrations/google-analytics/) for more information.

## Wishlisting

These events may occur if your ecommerce supports wishlist features.

### Product Added to Wishlist

Fire this event when a customer adds a product to their wish list.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>wishlist_id</td>
    <td>String</td>
    <td>Wishlist ID to which the product was added to</td>
  </tr>
  <tr>
    <td>wishlist_name</td>
    <td>String</td>
    <td>Wishlist name to which the product was added to</td>
  </tr>
  <tr>
    <td>product_id</td>
    <td>String</td>
    <td>Database id of the product being viewed</td>
  </tr>
  <tr>
    <td>sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>price</td>
    <td>Number</td>
    <td>Price ($) of the product being viewed</td>
  </tr>
  <tr>
    <td>quantity</td>
    <td>Number</td>
    <td>Quantity of a product</td>
  </tr>
  <tr>
    <td>coupon</td>
    <td>String</td>
    <td>Coupon code associated with a product (e.g MAY_DEALS_3)</td>
  </tr>
  <tr>
    <td>position</td>
    <td>Number</td>
    <td>Position in the product list (ex. 3)</td>
  </tr>
  <tr>
    <td>url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:

```js
analytics.track('Product Added to Wishlist', {
  wishlist_id: 'skdjsidjsdkdj29j',
  wishlist_name: 'Loved Games',
  product_id: '507f1f77bcf86cd799439011',
  sku: 'G-32',
  category: 'Games',
  name: 'Monopoly: 3rd Edition',
  brand: 'Hasbro',
  variant: '200 pieces',
  price: 18.99,
  quantity: 1,
  coupon: 'MAYDEALS',
  position: 3,
  url: 'https://www.example.com/product/path',
  image_url: 'https://www.example.com/product/path.jpg'
});
```

**Note:** The `sku` and `product_id` do not have to be different. If they are different, typically the `product_id` is a database identifier, like `9714107479` and the `sku` is a public-facing identifier like `SEG-02`.

### Product Removed from Wishlist

Fire this event when a customer removes a product from their wish list.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>wishlist_id</td>
    <td>String</td>
    <td>Wishlist ID to which the product was added to</td>
  </tr>
  <tr>
    <td>wishlist_name</td>
    <td>String</td>
    <td>Wishlist name to which the product was added to</td>
  </tr>
  <tr>
    <td>product_id</td>
    <td>String</td>
    <td>Database id of the product being viewed</td>
  </tr>
  <tr>
    <td>sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>price</td>
    <td>Number</td>
    <td>Price ($) of the product being viewed</td>
  </tr>
  <tr>
    <td>quantity</td>
    <td>Number</td>
    <td>Quantity of a product</td>
  </tr>
  <tr>
    <td>coupon</td>
    <td>String</td>
    <td>Coupon code associated with a product (e.g MAY_DEALS_3)</td>
  </tr>
  <tr>
    <td>position</td>
    <td>Number</td>
    <td>Position in the product list (ex. 3)</td>
  </tr>
  <tr>
    <td>url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:

```js
analytics.track('Product Removed from Wishlist', {
  wishlist_id: 'skdjsidjsdkdj29j',
  wishlist_name: 'Loved Games',
  product_id: '507f1f77bcf86cd799439011',
  sku: 'G-32',
  category: 'Games',
  name: 'Monopoly: 3rd Edition',
  brand: 'Hasbro',
  variant: '200 pieces',
  price: 18.99,
  quantity: 1,
  coupon: 'MAYDEALS',
  position: 3,
  url: 'https://www.example.com/product/path',
  image_url: 'https://www.example.com/product/path.jpg'
});
```

**Note:** The `sku` and `product_id` do not have to be different. If they are different, typically the `product_id` is a database identifier, like `9714107479` and the `sku` is a public-facing identifier like `SEG-02`.

### Wishlist Product Added to Cart

Fire this event when a customer moves a product from their wish list to their cart.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>wishlist_id</td>
    <td>String</td>
    <td>Wishlist ID to which the product was added to</td>
  </tr>
  <tr>
    <td>wishlist_name</td>
    <td>String</td>
    <td>Wishlist name to which the product was added to</td>
  </tr>
  <tr>
    <td>cart_id</td>
    <td>String</td>
    <td>Cart ID to which this product was added to</td>
  </tr>
  <tr>
    <td>product_id</td>
    <td>String</td>
    <td>Database ID of the product being viewed</td>
  </tr>
  <tr>
    <td>sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>price</td>
    <td>Number</td>
    <td>Price ($) of the product being viewed</td>
  </tr>
  <tr>
    <td>quantity</td>
    <td>Number</td>
    <td>Quantity of a product</td>
  </tr>
  <tr>
    <td>coupon</td>
    <td>String</td>
    <td>Coupon code associated with a product (e.g MAY_DEALS_3)</td>
  </tr>
  <tr>
    <td>position</td>
    <td>Number</td>
    <td>Position in the product list (ex. 3)</td>
  </tr>
  <tr>
    <td>url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:

```js
analytics.track('Wishlist Product Added to Cart', {
  wishlist_id: 'skdjsidjsdkdj29j',
  wishlist_name: 'Loved Games',
  cart_id: '99j2d92j9dj29dj29d2d',
  product_id: '507f1f77bcf86cd799439011',
  sku: 'G-32',
  category: 'Games',
  name: 'Monopoly: 3rd Edition',
  brand: 'Hasbro',
  variant: '200 pieces',
  price: 18.99,
  quantity: 1,
  coupon: 'MAYDEALS',
  position: 3,
  url: 'https://www.example.com/product/path',
  image_url: 'https://www.example.com/product/path.jpg'
});
```

**Note:** The `sku` and `product_id` do not have to be different. If they are different, typically the `product_id` is a database identifier, like `9714107479` and the `sku` is a public-facing identifier like `SEG-02`.

## Sharing

With many ecommerce stores integrating with social apps or other sharing capabilities, these events might be useful if you are tracking customers sharing product information.

### Product Shared

Fire this event when a customer shares a product.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>share_via</td>
    <td>String</td>
    <td>Method of sharing</td>
  </tr>
  <tr>
    <td>share_message</td>
    <td>String</td>
    <td>Message that the sender sent</td>
  </tr>
  <tr>
    <td>recipient</td>
    <td>String</td>
    <td>Recipient of the sharing</td>
  </tr>
  <tr>
    <td>product_id</td>
    <td>String</td>
    <td>Database ID of the product being viewed</td>
  </tr>
  <tr>
    <td>sku</td>
    <td>String</td>
    <td>Sku of the product being viewed</td>
  </tr>
  <tr>
    <td>category</td>
    <td>String</td>
    <td>Product category being viewed</td>
  </tr>
  <tr>
    <td>name</td>
    <td>String</td>
    <td>Name of the product being viewed</td>
  </tr>
  <tr>
    <td>brand</td>
    <td>String</td>
    <td>Brand associated with the product</td>
  </tr>
  <tr>
    <td>variant</td>
    <td>String</td>
    <td>Variant of the product (e.g. Black)</td>
  </tr>
  <tr>
    <td>price</td>
    <td>Number</td>
    <td>Price ($) of the product being viewed</td>
  </tr>
  <tr>
    <td>url</td>
    <td>String</td>
    <td>URL of the product page</td>
  </tr>
  <tr>
    <td>image_url</td>
    <td>String</td>
    <td>Image url of the product</td>
  </tr>
</table>

Example:

```js
analytics.track('Product Shared', {
  share_via: 'email',
  share_message: 'Hey, check out this item',
  recipient: 'friend@gmail.com',
  product_id: '507f1f77bcf86cd799439011',
  sku: 'G-32',
  category: 'Games',
  name: 'Monopoly: 3rd Edition',
  brand: 'Hasbro',
  variant: '200 pieces',
  price: 18.99,
  url: 'https://www.example.com/product/path',
  image_url: 'https://www.example.com/product/path.jpg'
});
```

**Note:** The `sku` and `product_id` do not have to be different. If they are different, typically the `product_id` is a database identifier, like `9714107479` and the `sku` is a public-facing identifier like `SEG-02`.

### Cart Shared

Fire this event when a customer shares a shopping cart.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>share_via</td>
    <td>String</td>
    <td>Method of sharing</td>
  </tr>
  <tr>
    <td>share_message</td>
    <td>String</td>
    <td>Message that the sender sent</td>
  </tr>
  <tr>
    <td>recipient</td>
    <td>String</td>
    <td>Recipient of the sharing</td>
  </tr>
  <tr>
    <td>cart_id</td>
    <td>String</td>
    <td>Shopping cart ID</td>
  </tr>
  <tr>
    <td>products</td>
    <td>Array<Product></td>
    <td>Products displayed in the product list</td>
  </tr>
  <tr>
    <td>products.$.product_id</td>
    <td>String</td>
    <td>Product id displayed on the list</td>
  </tr>
</table>

Example:
```js
analytics.track('Cart Viewed', {
  share_via: 'email',
  share_message: 'Hey, check out this item',
  recipient: 'friend@gmail.com',
  cart_id: 'd92jd29jd92jd29j92d92jd',
  products: [
    { product_id: '507f1f77bcf86cd799439011' },
    { product_id: '505bd76785ebb509fc183733' }
  ]
});
```

## Reviewing

These events can be useful for tracking product related reviews.

### Product Reviewed

Fire this event when a customer reviews a product.

This event supports the following semantic properties:

<table>
  <tr>
    <th>**Property**</th>
    <th>**Type**</th>
    <th>**Description**</th>
  </tr>
  <tr>
    <td>product_id</td>
    <td>String</td>
    <td>Product’s ID</td>
  </tr>
  <tr>
    <td>review_id</td>
    <td>String</td>
    <td>Review ID</td>
  </tr>
  <tr>
    <td>review_body</td>
    <td>String</td>
    <td>Review body</td>
  </tr>
  <tr>
    <td>rating</td>
    <td>String</td>
    <td>Review rating</td>
  </tr>
</table>

Example:
```js
analytics.track('Product Reviewed', {
  product_id: '507f1f77bcf86cd799439011',
  review_id: 'kdfjrj39fj39jf3',
  review_body: 'I love this product',
  rating: '5'
});
```