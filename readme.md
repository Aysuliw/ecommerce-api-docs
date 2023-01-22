
# E-commerce API Documentation 

URL - https://ecommerce-h6sh.onrender.com/


### The documentation is not complete yet

## Countries
#### Get all countries
```
fetch('https://ecommerce-h6sh.onrender.com/countries')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
[
  {
    "country_name": "string",
    "id": 1
  },
  /*...*/
  {
    "country_name": "string",
    "id": 10
  }
]
</pre>
</details>

#### Get a single country
```
fetch('https://ecommerce-h6sh.onrender.com/countries/1')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
    "country_name": "string",
    "id": 1
  }
</pre>
</details>


#### Limit results
```
fetch('https://ecommerce-h6sh.onrender.com/countries?limit=5&offset=5')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
[
  {
    "country_name": "string",
    "id": 5
  },
  /*...*/
  {
    "country_name": "string",
    "id": 10
  }
]
</pre>
</details>


#### Add new country
```
fetch('https://ecommerce-h6sh.onrender.com/countries',{
            method:"POST",
            body:JSON.stringify(
                {
                    country_name: 'new country name,
                }
            )
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
    "country_name": "string",
    "id": 11
  }
</pre>
</details>

#### Update a country
```
fetch('https://ecommerce-h6sh.onrender.com/countries/7',{
            method:"PUT",
            body:JSON.stringify(
                {
                    country_name: 'Updated country name,
                }
            )
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
    "country_name": "Updated country name",
    "id": 7
  }
</pre>
</details>

#### Delete a country
```
fetch('https://ecommerce-h6sh.onrender.com/countries/7',{
            method:"DELETE"
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
    "ok": True
  }
</pre>
</details>

## Categories

#### Get all categories
```
fetch('https://ecommerce-h6sh.onrender.com/categories')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
[
  {
    "name": "Электроника",
    "id": 1,
    "children_category": [
      {
        "name": "Телефоны и гаджеты",
        "id": 6
      }
    ],
    "parent_category": null
  },
  /*...*/
  {
    "name": "Телефоны и гаджеты",
    "id": 6,
    "children_category": [
      {
        "name": "Смартфоны",
        "id": 7
      }
    ],
    "parent_category": {
      "name": "Электроника",
      "id": 3
    }
  },
  {
    "name": "Смартфоны",
    "id": 7,
    "children_category": [],
    "parent_category": {
      "name": "Телефоны и гаджеты",
      "id": 6
    }
  }
]
</pre>
</details>

#### Get a single category
```
fetch('https://ecommerce-h6sh.onrender.com/categories/1')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
    "name": "Электроника",
    "id": 1,
    "children_category": [
      {
        "name": "Телефоны и гаджеты",
        "id": 6
      }
    ],
    "parent_category": null
  }
</pre>
</details>

#### Limit results
```
fetch('https://ecommerce-h6sh.onrender.com/categories?limit=5&offset=5')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
[
  {
    "name": "Электроника",
    "id": 5,
    "children_category": [
      {
        "name": "Телефоны и гаджеты",
        "id": 6
      }
    ],
    "parent_category": null
  },
  /*...*/
  {
    "name": "Телефоны и гаджеты",
    "id": 9,
    "children_category": [
      {
        "name": "Смартфоны",
        "id": 7
      }
    ],
    "parent_category": {
      "name": "Электроника",
      "id": 3
    }
  },
  {
    "name": "Смартфоны",
    "id": 10,
    "children_category": [],
    "parent_category": {
      "name": "Телефоны и гаджеты",
      "id": 6
    }
  }
]
</pre>
</details>

#### Add new category
```
fetch('https://ecommerce-h6sh.onrender.com/categories',{
            method:"POST",
            body:JSON.stringify(
                {
                   "name": "new category",
                   "parent_category_id": null/1
                }
            )
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
    "name": "new category",
    "id": 1,
    "children_category": [],
    "parent_category": {
        "name": "parent category",
        "id": 6
      }
  }
</pre>
</details>

#### Update a category
```
fetch('https://ecommerce-h6sh.onrender.com/categories/7',{
            method:"PUT",
            body:JSON.stringify(
                {
                   "name": "updated category",
                   "parent_category_id": null/int
                }
            )
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
    "name": "updated category",
    "id": 1,
    "children_category": [],
    "parent_category": {
        "name": "parent category",
        "id": 6
      }
  }
</pre>
</details>

#### Delete a category
```
fetch('https://ecommerce-h6sh.onrender.com/categories/7',{
            method:"DELETE"
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
    "ok": True
  }
</pre>
</details>


## Products

#### Get all products
```
fetch('https://ecommerce-h6sh.onrender.com/products/')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
[
     {
        "name": "iPhone",
        "price": 2000,
        "description": "Some description ....",
        "quantity": 50,
        "discount": 0,
        "id": 1,
        "images": [
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image1.png",
                "id": 1
            },
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image2.png",
                "id": 2
            }
        ],
        "category": {
            "name": "string",
            "id": 1,
            "children_category": [],
            "parent_category": null
        }
    },
    /*...*/
    {
        "name": "TV",
        "price": 500,
        "description": "Some description ....",
        "quantity": 100,
        "discount": 0,
        "id": 10,
        "images": [
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image1.png",
                "id": 1
            },
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image2.png",
                "id": 2
            }
        ],
        "category": {
            "name": "string",
            "id": 5,
            "children_category": [],
            "parent_category": null
        }
    }
]
</pre>
</details>

#### Limit products
```
fetch('https://ecommerce-h6sh.onrender.com/products?limit=5')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
[
     {
        "name": "iPhone",
        "price": 2000,
        "description": "Some description ....",
        "quantity": 50,
        "discount": 0,
        "id": 1,
        "images": [
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image1.png",
                "id": 1
            },
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image2.png",
                "id": 2
            }
        ],
        "category": {
            "name": "string",
            "id": 1,
            "children_category": [],
            "parent_category": null
        }
    },
    /*...*/
    {
        "name": "TV",
        "price": 500,
        "description": "Some description ....",
        "quantity": 100,
        "discount": 0,
        "id": 5,
        "images": [
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image1.png",
                "id": 1
            },
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image2.png",
                "id": 2
            }
        ],
        "category": {
            "name": "string",
            "id": 5,
            "children_category": [],
            "parent_category": null
        }
    }
]
</pre>
</details>

#### Get products by category
```
fetch('https://ecommerce-h6sh.onrender.com/categories/1/products/')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
[
     {
        "name": "iPhone",
        "price": 2000,
        "description": "Some description ....",
        "quantity": 50,
        "discount": 0,
        "id": 1,
        "images": [
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image1.png",
                "id": 1
            },
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image2.png",
                "id": 2
            }
        ],
        "category": {
            "name": "string",
            "id": 1,
            "children_category": [],
            "parent_category": null
        }
    },
    /*...*/
    {
        "name": "TV",
        "price": 500,
        "description": "Some description ....",
        "quantity": 100,
        "discount": 0,
        "id": 5,
        "images": [
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image1.png",
                "id": 1
            },
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image2.png",
                "id": 2
            }
        ],
        "category": {
            "name": "string",
            "id": 1,
            "children_category": [],
            "parent_category": null
        }
    }
]
</pre>
</details>


#### Get a single product
```
fetch('https://ecommerce-h6sh.onrender.com/products/1')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
     {
        "name": "iPhone",
        "price": 2000,
        "description": "Some description ....",
        "quantity": 50,
        "discount": 0,
        "id": 1,
        "images": [
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image1.png",
                "id": 1
            },
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image2.png",
                "id": 2
            }
        ],
        "category": {
            "name": "Электроника",
            "id": 1,
            "children_category": [],
            "parent_category": null
        }
    }
</pre>
</details>


#### Add new product
```
fetch('https://ecommerce-h6sh.onrender.com/products',{
            method:"POST",
            body:JSON.stringify(
                {
                    "product": {
                        "name": "iPhone",
                        "price": 2000,
                        "description": "Some description here",
                        "quantity": 50,
                        "discount": 0,
                        "category_id": 1
                    },
                    "product_images": [
                        {
                            "image_path": "www.test.com/product_image1"
                        },
                        {
                            "image_path": "www.test.com/product_image2"
                        }
                    ]
                }
            )
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
     {
        "name": "iPhone",
        "price": 2000,
        "description": "Some description ....",
        "quantity": 50,
        "discount": 0,
        "id": 1,
        "images": [
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image1.png",
                "id": 1
            },
            {
                "product_id": 1,
                "product_variants_id": null,
                "image_path": "www.website.com/product_image2.png",
                "id": 2
            }
        ],
        "category": {
            "name": "Электроника",
            "id": 1,
            "children_category": [],
            "parent_category": null
        }
    }
</pre>
</details>

#### Update a product
```
fetch('https://ecommerce-h6sh.onrender.com/products/1',{
            method:"PUT",
            body:JSON.stringify(
                {
                    "name": "iPhone new",
                    "price": 1000,
                    "description": "Some description here updated",
                    "quantity": 100,
                    "discount": 10,
                    "category_id": 1
                }
            )
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
      "name": "iPhone new",
      "price": 1000,
      "description": "Some description here updated",
      "quantity": 100,
      "discount": 10,
      "id": 1,
      "images": [
          {
              "product_id": 1,
              "product_variants_id": null,
              "image_path": "www.website.com/product_image1.png",
              "id": 1
          },
          {
              "product_id": 1,
              "product_variants_id": null,
              "image_path": "www.website.com/product_image2.png",
              "id": 2
          }
      ],
      "category": {
          "name": "Электроника",
          "id": 1,
          "children_category": [],
          "parent_category": null
      }
  }
</pre>
</details>

#### Delete a product
```
fetch('https://ecommerce-h6sh.onrender.com/products/7',{
            method:"DELETE"
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
    "ok": True
  }
</pre>
</details>


## Users
#### Get all users
```
fetch('https://ecommerce-h6sh.onrender.com/users/')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>

[
    {
        "username": "string",
        "is_admin": true,
        "id": 1,
        "user_detail": {
            "first_name": "Any name",
            "last_name": "Any surname",
            "user_image": "www.somewebsite.com/user1.jpg",
            "id": 1
        },
        "phone_numbers": [
            {
                "phone_number": "+998991234567",
                "type": "mobile",
                "id": 1
            }
        ],
        "addresses": [
            {
                "street_address": "street 50",
                "postal_code": "123100",
                "city": "Nukus",
                "id": 1,
                "country": {
                    "country_name": "Uzbekistan",
                    "id": 2
                }
            }
        ]
    }, 
    /***/
    {},
    {}
]
</pre>
</details>

#### Limit results
```
fetch('https://ecommerce-h6sh.onrender.com/users?limit=5')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>

[
    {
        "username": "string",
        "is_admin": true,
        "id": 1,
        "user_detail": {
            "first_name": "Any name",
            "last_name": "Any surname",
            "user_image": "www.somewebsite.com/user1.jpg",
            "id": 1
        },
        "phone_numbers": [
            {
                "phone_number": "+998991234567",
                "type": "mobile",
                "id": 1
            }
        ],
        "addresses": [
            {
                "street_address": "street 50",
                "postal_code": "123100",
                "city": "Nukus",
                "id": 1,
                "country": {
                    "country_name": "Uzbekistan",
                    "id": 2
                }
            }
        ]
    }, 
    /***/
    {"id":5},
]
</pre>
</details>

#### Get a single user
```
fetch('https://ecommerce-h6sh.onrender.com/users/1')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
{
    "username": "string",
    "is_admin": true,
    "id": 1,
    "user_detail": {
        "first_name": "Any name",
        "last_name": "Any surname",
        "user_image": "www.somewebsite.com/user1.jpg",
        "id": 1
    },
    "phone_numbers": [
        {
            "phone_number": "+998991234567",
            "type": "mobile",
            "id": 1
        }
    ],
    "addresses": [
        {
            "street_address": "street 50",
            "postal_code": "123100",
            "city": "Nukus",
            "id": 1,
            "country": {
                "country_name": "Uzbekistan",
                "id": 2
            }
        }
    ]
}
</pre>
</details>


#### Add new user
```
fetch('https://ecommerce-h6sh.onrender.com/users',{
            method:"POST",
            body:JSON.stringify(
                {
                    "user": {
                        "username": "string",
                        "is_admin": false,
                        "password": "string"
                    },
                    "user_detail": {
                        "first_name": "Any name",
                        "last_name": "Any surname",
                        "user_image": "www.somewebsite.com/user1.jpg"
                    },
                    "user_phones": [
                        {
                            "phone_number": "+998991234567",
                            "type": "mobile"
                        }
                    ],
                    "user_address": {
                        "street_address": "street 50",
                        "postal_code": "123100",
                        "city": "Nukus",
                        "country_id": 2
                    }
                }
            )
        })
        .then(res=>res.json())
        .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
{
    "username": "string",
    "is_admin": true,
    "id": 1,
    "user_detail": {
        "first_name": "Any name",
        "last_name": "Any surname",
        "user_image": "www.somewebsite.com/user1.jpg",
        "id": 1
    },
    "phone_numbers": [
        {
            "phone_number": "+998991234567",
            "type": "mobile",
            "id": 1
        }
    ],
    "addresses": [
        {
            "street_address": "street 50",
            "postal_code": "123100",
            "city": "Nukus",
            "id": 1,
            "country": {
                "country_name": "Uzbekistan",
                "id": 2
            }
        }
    ]
}
</pre>
</details>

#### Update a user
```
fetch('https://ecommerce-h6sh.onrender.com/users/7',{
            method:"PUT",
            body:JSON.stringify(
                {
                    "user": {
                        "username": "new username",
                        "is_admin": true
                    },
                    "user_detail": {
                        "first_name": "new name",
                        "last_name": "Mambnew updated surname",
                        "user_image": "www.somewebsite.com/user1.jpg"
                    }
                }
            )
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
    {
        "username": "new username",
        "is_admin": true,
        "id": 1,
        "user_detail": {
            "first_name": "new name",
            "last_name": "new updated surname",
            "user_image": "www.somewebsite.com/user1.jpg",
            "id": 1
        },
        "phone_numbers": [
            {
                "phone_number": "+998991234567",
                "type": "mobile",
                "id": 1
            }
        ],
        "addresses": [
            {
                "street_address": "street 50",
                "postal_code": "123100",
                "city": "Nukus",
                "id": 1,
                "country": {
                    "country_name": "Uzbekistan",
                    "id": 2
                }
            }
        ]
    }
</pre>
</details>

#### Delete a user
```
fetch('https://ecommerce-h6sh.onrender.com/users/7',{
            method:"DELETE"
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
    "ok": True
  }
</pre>
</details>


## Attributes

#### Get category attributes
```
fetch('https://ecommerce-h6sh.onrender.com/categories/{category_id}/attributes')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
[
  {
    "attribute_name": "color",
    "category_id": 1,
    "id": 1,
    "variants": {
      "value": "green",
      "id": 1
    },
    {
      "value": "red",
      "id": 2
    }
  },
  /*...*/
  {
    "attribute_name": "size",
    "category_id": 1,
    "id": 10,
    "variants": {
      "value": "300",
      "id": 5
    },
    {
      "value": "500",
      "id": 6
    }
  },
]
</pre>
</details>

#### Get a single attribute
```
fetch('https://ecommerce-h6sh.onrender.com/attributes/1')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
    "attribute_name": "color",
    "category_id": 1,
    "id": 1,
    "variants": {
      "value": "green",
      "id": 1
    },
    {
      "value": "red",
      "id": 2
    }
  },
</pre>
</details>


#### Limit results
```
fetch('https://ecommerce-h6sh.onrender.com/categories/{category_id}/attributes?limit=5&offset=0')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
[
  {
    "attribute_name": "color",
    "category_id": 1,
    "id": 1,
    "variants": {
      "value": "green",
      "id": 1
    },
    {
      "value": "red",
      "id": 2
    }
  },
  /*...*/
  {
    "attribute_name": "size",
    "category_id": 1,
    "id": 5,
    "variants": {
      "value": "300",
      "id": 5
    },
    {
      "value": "500",
      "id": 6
    }
  },
]
</pre>
</details>


#### Add new attribute
```
fetch('https://ecommerce-h6sh.onrender.com/attributes',{
            method:"POST",
            body:JSON.stringify(
                {
                  "attribute": {
                    "attribute_name": "color",
                    "category_id": 1
                  },
                  "variants": [
                    {
                      "value": "red"
                    },
                    {
                      "value": "green"
                    }
                  ]
                }
            )
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
    "attribute_name": "color",
    "category_id": 1,
    "id": 5
    "variants": [
        {
            "id": 7,
            "value": "red"
        },
        {
            "id": 8,
            "value": "green"
        }
    ]
  }
</pre>
</details>

#### Update an attribute
```
fetch('https://ecommerce-h6sh.onrender.com/attributes/7',{
            method:"PUT",
            body:JSON.stringify(
                {
                    "attribute_name": 'Updated attribute name,
                    "category_id": 12
                }
            )
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
{
  "attribute_name": "updated attribute name",
  "category_id": 12,
  "id": 2,
  "variants": [
    {
      "value": "green",
      "id": 3
    },
    {
      "value": "red",
      "id": 4
    }
  ]
}
</pre>
</details>

#### Delete an attribute
```
fetch('https://ecommerce-h6sh.onrender.com/attributes/7',{
            method:"DELETE"
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
    "ok": True
  }
</pre>
</details>

