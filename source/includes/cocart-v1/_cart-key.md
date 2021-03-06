# Cart Key #

<img src="images/github.svg" width="20" height="20" alt="GitHub Mark Logo"> [Edit on GitHub](https://github.com/co-cart/co-cart-docs/blob/master/source/includes/cocart-v1/_cart_key.md)

## What is a Cart Key? ##

A cart key is what identifies the cart stored in session along with it's cart data and expiration. This is normally stored in a [cookie](#cookie) and is used to load the cart in session if the cart still exists.

## Accessing the Cart Key ##

If cookies don't work for you due to the limitations of the framework your using to build with, then don't worry. The cart key created for the customer is returned via the returned headers once the first API request has been made. This is helpful for supporting guest customers.

Look for `X-CoCart-API` and you will see the value of the cart key returned. You can then use this to set any of the CoCart API to load this cart when required using the `cart_key` parameter.

<aside class="warning">
    The <code>cart_key</code> parameter is a global parameter so it must be queried rather than being added as part of the data you send with the API request you make. Otherwise it will not update the cart.
</aside>

## Cart Key in Cart Response ##

It's also possible to return the cart key when you [get the cart](#get-cart). Simply download and activate the [Get Cart Enhanced add-on plugin](#cocart-add-ons-get-cart-enhanced) and the cart key is returned along with other enhancements in the response.
