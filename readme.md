
# E-commerce API Documentation 

URL - http://147.45.107.233/api/
.

### The documentation is not complete yet

Structure of documentation

- [Users](#users)
  - [Registration](#registration)
- [Categories](#categories)
  - [Get all categories](#get-all-categories)
  - [Get a single category](#get-a-single-category)
- [Products](#products)
   - [Get all products](#get-all-products)
   - [Get products by category](#get-products-by-category)
   - [Sort products](#sort-products)
   - [Get a single product](#get-a-single-product)

## Users
### Registration
```
http://147.45.107.233/api/users
POST Request  Content-Type: application/json
body:
{
    "first_name": "str",
    "last_name": "str",
    "password": "str",
    "phone": "998991234567",
    "date_of_birth": 2000-10-23, (Format: YYYY-MM-DD)
    "gender": "male"  (Choices: "male"/"female")
} 
```

<details><summary>Response</summary>
<pre>
{
    "success": true,
    "errMessage": null,
    "errorCode": null,
    "data": {
        "user": {
            "id": 6,
            "first_name": "Name",
            "last_name": "Surname",
            "phone": "998991234567",
            "date_of_birth": "2000-02-10",
            "gender": "male",
            "is_active": False,
        }
    }
}
</pre>
</details>

### Verification (OTP)
```
http://147.45.107.233/api/users/{pk}/verify
POST request Content-Type: application/json
body:
{
    "otp": "524687"  (Expire time: 1 min)
} 
```

<details><summary>Response</summary>
<pre>
{
    "success": true,
    "errMessage": null,
    "errorCode": null
}
</pre>
</details>


### Ask Code again (Qaytadan kod soraw)
```
http://147.45.107.233/api/users/{pk}/otp
POST request Content-Type: application/json
```

<details><summary>Response</summary>
<pre>
{
    "success": true,
    "errMessage": null,
    "errorCode": null
}
</pre>
</details>

## Categories

#### Get all categories
```
http://147.45.107.233/api/categories 
```

<details><summary>Output</summary>
<pre>
{
    "success": true,
    "errorMessage": null,
    "errorCode": null,
    "data": {
        "categories": [
            {
                "id": 1,
                "name": "Товары для детей",
                "parent_category": null
            },
            {
                "id": 2,
                "name": "Головные уборы и перчатки",
                "parent_category": 1
            },
            {
                "id": 3,
                "name": "Комбинезоны для новорожденных",
                "parent_category": 1
            },
            {
                "id": 5,
                "name": "Готовые сумки в роддом",
                "parent_category": 4
            }
        ]
    }
}
</pre>
</details>

#### Get a single category
```
http://147.45.107.233/api/categories/1
```

<details><summary>Output</summary>
<pre>
{
    "success": true,
    "errorMessage": null,
    "errorCode": null,
    "data": {
        "categories": {
            "id": 1,
            "name": "Товары для детей",
            "parent_category": null
        }
    }
}
</pre>
</details>

## Products

#### Get all products
```
http://147.45.107.233/api/products?limit=5&offset=0
```

<details><summary>Output</summary>
<pre>
{
    "success": true,
    "errMessage": null,
    "errorCode": null,
    "data": {
        "items": [
            {
                "id": 132,
                "code": "10131",
                "name": "BENKUNG 18M",
                "description": null,
                "price": 200000,
                "amount": 1,
                "category": 7,
                "images": [
                    {
                        "id": 132,
                        "image": "http://147.45.107.233/media/products/product.png"
                    }
                ]
            },
            {
                "id": 133,
                "code": "10132",
                "name": "10349 TOLSTOVKA MALCHIK",
                "description": null,
                "price": 200000,
                "amount": 2,
                "category": 8,
                "images": [
                    {
                        "id": 133,
                        "image": "http://147.45.107.233/media/products/product.png"
                    }
                ]
            },
            {
                "id": 134,
                "code": "10133",
                "name": "10332 TOLSTOVKA DEVOCHKA",
                "description": null,
                "price": 200000,
                "amount": 1,
                "category": 9,
                "images": [
                    {
                        "id": 134,
                        "image": "http://147.45.107.233/media/products/product.png"
                    }
                ]
            }
        ],
        "total_records": 238,
        "next": "http://147.45.107.233/api/products?limit=3&max_price=380000&min_price=200000&offset=3&ordering=ascending&sorting=price",
        "previous": null
    }
}
</pre>
</details>

#### Get products by category
```
http://147.45.107.233/api/products?category={category_id}
```

<details><summary>Output</summary>
<pre>
{
    "success": true,
    "errMessage": null,
    "errorCode": null,
    "data": {
        "items": [
            {
                "id": 1,
                "code": "10000",
                "name": "BORTIK DET KROVAT",
                "description": null,
                "price": 720000,
                "amount": 3,
                "category": 2,
                "images": [
                    {
                        "id": 1,
                        "image": "http://147.45.107.233/media/products/product.png"
                    }
                ]
            },
            {
                "id": 9,
                "code": "10008",
                "name": "KOMBINEZON",
                "description": null,
                "price": 420000,
                "amount": 2,
                "category": 2,
                "images": [
                    {
                        "id": 9,
                        "image": "http://147.45.107.233/media/products/product.png"
                    }
                ]
            },
            {
                "id": 17,
                "code": "10016",
                "name": "VECHER PLATYA",
                "description": null,
                "price": 400000,
                "amount": 5,
                "category": 2,
                "images": [
                    {
                        "id": 17,
                        "image": "http://147.45.107.233/media/products/product.png"
                    }
                ]
            }
        ],
        "total_records": 170,
        "next": "http://147.45.107.233/api/products?category=2&limit=3&offset=3",
        "previous": null
    }
}
</pre>
</details>


#### Sort products

Sort products by price ascending or descending order
> **http://147.45.107.233/api/products?sorting=price&ordering=ascending**  
> **http://147.45.107.233/api/products?sorting=price&ordering=descending**

#### Sort products in range min_price and max_price
> **http://147.45.107.233/api/products?min_price=1000&max_price=500000**  

#### Get a single product
```
http://147.45.107.233/api/products/1
```

<details><summary>Output</summary>
<pre>
     {
    "success": true,
    "errorMessage": null,
    "errorCode": null,
    "data": {
        "items": {
            "id": 2,
            "code": "10001",
            "name": "ROZOVIY SHIFON PLATYE",
            "description": null,
            "price": 550000,
            "amount": 3,
            "category": 3,
            "images": [
                {
                    "id": 2,
                    "image": "http://147.45.107.233/media/products/product.png"
                }
            ]
        }
    }
}
</pre>
</details>


