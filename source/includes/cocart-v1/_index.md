# Index #

<img src="images/github.svg" width="20" height="20" alt="GitHub Mark Logo"> [Edit on GitHub](https://github.com/co-cart/co-cart-docs/blob/master/source/includes/cocart-v1/_index.md)

By default, the API provides information about all available endpoints on the site. Authentication is not required to access the API index.

<aside class="notice">
    Some endpoints are only available in CoCart Pro or via add-on.
</aside>

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/cocart/v1</h6>
	</div>
</div>

```shell
curl -X GET https://example.com/wp-json/cocart/v1 \
  -H "Content-Type: application/json"
```

```javascript--jquery
var settings = {
  "url": "https://example.com/wp-json/cocart/v1",
  "method": "GET"
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php
$curl = curl_init();

curl_setopt_array( $curl, array(
  CURLOPT_URL => "https://example.com/wp-json/cocart/v1",
  CURLOPT_CUSTOMREQUEST => "GET",
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
$response = wp_remote_get( 'https://example.com/wp-json/cocart/v1' );
$body = wp_remote_retrieve_body( $response );
```

> JSON response example:

```json
{
    "namespace": "cocart/v1",
    "routes": {
        "/cocart/v1": {
            "namespace": "cocart/v1",
            "methods": [
                "GET"
            ],
            "endpoints": [
                {
                    "methods": [
                        "GET"
                    ],
                    "args": {
                        "namespace": {
                            "required": false,
                            "default": "cocart/v1"
                        },
                        "context": {
                            "required": false,
                            "default": "view"
                        }
                    }
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v1"
                    }
                ]
            }
        },
        "/cocart/v1/get-cart": {
            "namespace": "cocart/v1",
            "methods": [
                "GET"
            ],
            "endpoints": [
                {
                    "methods": [
                        "GET"
                    ],
                    "args": {
                        "cart_key": {
                            "required": false,
                            "description": "Unique identifier for the cart/customer.",
                            "type": "string"
                        },
                        "thumb": {
                            "required": false,
                            "default": false,
                            "description": "Returns the URL of the product image thumbnail.",
                            "type": "boolean"
                        }
                    }
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v1/get-cart"
                    }
                ]
            }
        },
        "/cocart/v1/get-cart/(?P<id>[\\w]+)": {
            "namespace": "cocart/v1",
            "methods": [
                "GET"
            ],
            "endpoints": [
                {
                    "methods": [
                        "GET"
                    ],
                    "args": {
                        "cart_key": {
                            "required": false,
                            "description": "Unique identifier for the cart/customer.",
                            "type": "string"
                        },
                        "thumb": {
                            "required": false,
                            "default": false,
                            "description": "Returns the URL of the product image thumbnail.",
                            "type": "boolean"
                        }
                    }
                }
            ]
        },
        "/cocart/v1/get-cart/customer/(?P<id>[\\d]+)": {
            "namespace": "cocart/v1",
            "methods": [
                "GET"
            ],
            "endpoints": [
                {
                    "methods": [
                        "GET"
                    ],
                    "args": {
                        "cart_key": {
                            "required": false,
                            "description": "Unique identifier for the cart/customer.",
                            "type": "string"
                        },
                        "thumb": {
                            "required": false,
                            "default": false,
                            "description": "Returns the URL of the product image thumbnail.",
                            "type": "boolean"
                        }
                    }
                }
            ]
        },
        "/cocart/v1/add-item": {
            "namespace": "cocart/v1",
            "methods": [
                "POST"
            ],
            "endpoints": [
                {
                    "methods": [
                        "POST"
                    ],
                    "args": {
                        "product_id": {
                            "required": false,
                            "description": "Unique identifier for the product.",
                            "type": "string"
                        },
                        "quantity": {
                            "required": true,
                            "default": 1,
                            "description": "The quantity amount of the item to add to cart.",
                            "type": "float"
                        },
                        "variation_id": {
                            "required": false,
                            "description": "Unique identifier for the variation.",
                            "type": "integer"
                        },
                        "variation": {
                            "required": false,
                            "description": "The variation attributes that identity the variation of the item.",
                            "type": "array"
                        },
                        "cart_item_data": {
                            "required": false,
                            "description": "Additional item data passed to make item unique.",
                            "type": "array"
                        },
                        "return_cart": {
                            "required": false,
                            "default": false,
                            "description": "Returns the cart once item is added.",
                            "type": "boolean"
                        }
                    }
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v1/add-item"
                    }
                ]
            }
        },
        "/cocart/v1/clear": {
            "namespace": "cocart/v1",
            "methods": [
                "POST"
            ],
            "endpoints": [
                {
                    "methods": [
                        "POST"
                    ],
                    "args": []
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v1/clear"
                    }
                ]
            }
        },
        "/cocart/v1/calculate": {
            "namespace": "cocart/v1",
            "methods": [
                "POST"
            ],
            "endpoints": [
                {
                    "methods": [
                        "POST"
                    ],
                    "args": {
                        "return": {
                            "required": false,
                            "default": false,
                            "description": "Returns the cart totals once calculated.",
                            "type": "boolean"
                        }
                    }
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v1/calculate"
                    }
                ]
            }
        },
        "/cocart/v1/count-items": {
            "namespace": "cocart/v1",
            "methods": [
                "GET"
            ],
            "endpoints": [
                {
                    "methods": [
                        "GET"
                    ],
                    "args": {
                        "return": {
                            "required": false,
                            "default": "numeric"
                        }
                    }
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v1/count-items"
                    }
                ]
            }
        },
        "/cocart/v1/item": {
            "namespace": "cocart/v1",
            "methods": [
                "GET",
                "POST",
                "DELETE"
            ],
            "endpoints": [
                {
                    "methods": [
                        "GET"
                    ],
                    "args": {
                        "cart_item_key": {
                            "required": false,
                            "description": "Unique identifier for the item in the cart.",
                            "type": "string"
                        },
                        "return_cart": {
                            "required": false,
                            "default": false,
                            "description": "Returns the whole cart to reduce API requests.",
                            "type": "boolean"
                        }
                    }
                },
                {
                    "methods": [
                        "POST"
                    ],
                    "args": {
                        "cart_item_key": {
                            "required": false,
                            "description": "Unique identifier for the item in the cart.",
                            "type": "string"
                        },
                        "return_cart": {
                            "required": false,
                            "default": false,
                            "description": "Returns the whole cart to reduce API requests.",
                            "type": "boolean"
                        },
                        "quantity": {
                            "required": false,
                            "default": 1,
                            "type": "float"
                        }
                    }
                },
                {
                    "methods": [
                        "DELETE"
                    ],
                    "args": {
                        "cart_item_key": {
                            "required": false,
                            "description": "Unique identifier for the item in the cart.",
                            "type": "string"
                        },
                        "return_cart": {
                            "required": false,
                            "default": false,
                            "description": "Returns the whole cart to reduce API requests.",
                            "type": "boolean"
                        }
                    }
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v1/item"
                    }
                ]
            }
        },
        "/cocart/v1/logout": {
            "namespace": "cocart/v1",
            "methods": [
                "POST"
            ],
            "endpoints": [
                {
                    "methods": [
                        "POST"
                    ],
                    "args": []
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v1/logout"
                    }
                ]
            }
        },
        "/cocart/v1/totals": {
            "namespace": "cocart/v1",
            "methods": [
                "GET"
            ],
            "endpoints": [
                {
                    "methods": [
                        "GET"
                    ],
                    "args": {
                        "html": {
                            "required": false,
                            "default": false,
                            "description": "Returns the totals pre-formatted.",
                            "type": "boolean"
                        }
                    }
                }
            ],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/cocart/v1/totals"
                    }
                ]
            }
        }
    },
    "_links": {
        "up": [
            {
                "href": "https://example.com/wp-json/"
            }
        ]
    }
}
```
