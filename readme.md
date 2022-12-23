
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



