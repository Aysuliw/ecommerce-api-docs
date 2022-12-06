
# E-commerce API Documentation 

URLS


## Countries
#### Get all countries
```
fetch('https://web-production-ed9c.up.railway.app/countries')
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
fetch('https://web-production-ed9c.up.railway.app/countries/1')
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


#### Add new country
```
fetch('https://web-production-ed9c.up.railway.app/countries',{
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
fetch('https://web-production-ed9c.up.railway.app/countries/7',{
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
fetch('https://web-production-ed9c.up.railway.app/countries/7',{
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
fetch('https://web-production-ed9c.up.railway.app/categories')
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
fetch('https://web-production-ed9c.up.railway.app/categories/1')
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


#### Add new category
```
fetch('https://web-production-ed9c.up.railway.app/categories',{
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
fetch('https://web-production-ed9c.up.railway.app/categories/7',{
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
fetch('https://web-production-ed9c.up.railway.app/categories/7',{
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

#### Get all attributes
```
fetch('https://web-production-ed9c.up.railway.app/attributes')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
[
  {
    "attribute_name": "color",
    "category_id": 7,
    "id": 1
  },
  {
    "attribute_name": "size",
    "category_id": 7,
    "id": 2
  },
  {
    "attribute_name": "brand",
    "category_id": 7,
    "id": 3
  }
]
</pre>
</details>

#### Get a single attribute
```
fetch('https://web-production-ed9c.up.railway.app/attributes/1')
            .then(res=>res.json())
            .then(json=>console.log(json))
```

<details><summary>Output</summary>
<pre>
  {
    "attribute_name": "color",
    "category_id": 7,
    "id": 1
  }
</pre>
</details>


#### Add new attribute
```
fetch('https://web-production-ed9c.up.railway.app/attributes',{
            method:"POST",
            body:JSON.stringify(
                {
                  "attribute_name": "string",
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
      "attribute_name": "string",
      "category_id": 1,
      "id": 1
    }
</pre>
</details>

#### Update an attribute
```
fetch('https://web-production-ed9c.up.railway.app/attributes/7',{
            method:"PUT",
            body:JSON.stringify(
                {
                  "attribute_name": "string",
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
      "attribute_name": "string",
      "category_id": 1,
      "id": 7
    }
</pre>
</details>

#### Delete an attribute
```
fetch('https://web-production-ed9c.up.railway.app/attributes/7',{
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
fetch('https://web-production-ed9c.up.railway.app/users')
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
      "first_name": "string",
      "last_name": "string",
      "user_image": "string",
      "id": 2
    },
    "phone_numbers": [
      {
        "phone_number": "+998994522958",
        "type": "mobile",
        "id": 1
      }
    ],
    "addresses": [
      {
        "street_address": "string",
        "postal_code": "string",
        "city": "string",
        "id": 2,
        "country": {
          "country_name": "Uzbekistan",
          "id": 1
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

#### Get a single user
```
fetch('https://web-production-ed9c.up.railway.app/users/1')
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
      "first_name": "string",
      "last_name": "string",
      "user_image": "string",
      "id": 2
    },
    "phone_numbers": [
      {
        "phone_number": "+998994522958",
        "type": "mobile",
        "id": 1
      }
    ],
    "addresses": [
      {
        "street_address": "string",
        "postal_code": "string",
        "city": "string",
        "id": 2,
        "country": {
          "country_name": "Uzbekistan",
          "id": 1
        }
      }
    ]
  }
</pre>
</details>


#### Add new user
```
fetch('https://web-production-ed9c.up.railway.app/users',{
            method:"POST",
            body:JSON.stringify(
                {
                  "user": {
                    "first_name": "string",
                    "last_name": "string",
                    "user_image": "string",
                    "username": "string",
                    "is_admin": true,
                    "password": "string"
                  },
                  "user_phones": [
                    {
                      "phone_number": "string",
                      "type": "string"
                    }
                  ],
                  "user_address": {
                    "street_address": "string",
                    "postal_code": "string",
                    "city": "string",
                    "country_id": 1
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
        "first_name": "string",
        "last_name": "string",
        "user_image": "string",
        "id": 2
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
          "street_address": "string",
          "postal_code": "string",
          "city": "string",
          "id": 2,
          "country": {
            "country_name": "Uzbekistan",
            "id": 1
          }
        }
      ]
    }
</pre>
</details>

#### Update a user
```
fetch('https://web-production-ed9c.up.railway.app/users/7',{
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

#### Delete a user
```
fetch('https://web-production-ed9c.up.railway.app/users/7',{
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
fetch('https://web-production-ed9c.up.railway.app/products')
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

#### Get a single product
```
fetch('https://web-production-ed9c.up.railway.app/products/1')
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


#### Add new product
```
fetch('https://web-production-ed9c.up.railway.app/products',{
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

#### Update a product
```
fetch('https://web-production-ed9c.up.railway.app/products/7',{
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

#### Delete a product
```
fetch('https://web-production-ed9c.up.railway.app/products/7',{
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


## Orders
#### Get all orders
```
fetch('https://web-production-ed9c.up.railway.app/countries')
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

#### Get a single order
```
fetch('https://web-production-ed9c.up.railway.app/orders/1')
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


#### Add new order
```
fetch('https://web-production-ed9c.up.railway.app/orders',{
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

#### Update an order
```
fetch('https://web-production-ed9c.up.railway.app/orders/7',{
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

#### Delete an order
```
fetch('https://web-production-ed9c.up.railway.app/orders/7',{
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



