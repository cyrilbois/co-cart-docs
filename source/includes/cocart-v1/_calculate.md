## Calculate Cart Totals ##

<img src="images/github.svg" width="20" height="20" alt="GitHub Mark Logo"> [Edit on GitHub](https://github.com/co-cart/co-cart-docs/blob/master/source/includes/cocart-v1/_calculate.md)

This API helps you calculate the cart totals. You can also request to return the totals once calculated to reduce API requests and use the [Retrieve Cart Totals](#totals-retrieve-cart-totals) properties.

### Properties ###

| Property   | Type   | Description                                                                                                                 |
| ---------- | ------ | --------------------------------------------------------------------------------------------------------------------------- |
| `cart_key` | string | Unique identifier for the cart. <a class="label label-info" href="#cart-key">?</a> <i class="label label-info">optional</i> |
| `return`   | bool   | Set as true to return the totals once calculated. <i class="label label-info">optional</i>                                  |

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/cocart/v1/calculate</h6>
	</div>
</div>

```shell
curl -X POST https://example.com/wp-json/cocart/v1/calculate \
	-H "Content-Type: application/json"
```

```javascript--jquery
var settings = {
  "url": "https://example.com/wp-json/cocart/v1/calculate",
  "method": "POST"
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php
$curl = curl_init();

curl_setopt_array( $curl, array(
  CURLOPT_URL => "https://example.com/wp-json/cocart/v1/calculate",
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTPHEADER => array(
    'Accept: application/json',
    'Content-Type: application/json',
    'User-Agent: CoCart API/v1',
  )
) );

$response = curl_exec($curl);

curl_close($curl);

echo $response;
```

```php--wp-http-api
<?php
$response = wp_remote_post( 'https://example.com/wp-json/cocart/v1/calculate' );
$body = wp_remote_retrieve_body( $response );
```

> JSON response example

```json
"Cart totals have been calculated."
```
