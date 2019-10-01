A product catalogue experience based on two sample APIs.

### Product lists
    http://127.0.0.1:3000/api/products

### Product details
    http://127.0.0.1:3000/api/product/$id  

### Requirements

* Implement pagination/infinite scroll
* Filters and sorts (eg. lowest price first, select a size)
* A mix of server and clientside rendering
* It should be device agnostic
* A quick view or extended view for product

The following are examples of the existing mobile and desktop listing pages:

* [Mobile](public/images/mobile.jpg)
* [Desktop](public/images/desktop.jpg)

## Setup

To run the app:

```shell
$ npm install
$ npm start
```

# Apis

## Products

Returns a list of products.

Example:

```
GET /api/products/?offset=0&limit=60
HTTP 200
Content-Type: application/json

{
    "offset": 0,
    "limit": 60,
    "total": 274,
    "data": [{
        "id": 540559,
        "name": "Roadmaster Waxed-Cotton Jacket",
        "price": "£550",
        "designer": "Belstaff",
        "image": {
            outfit: "//cache.net-a-porter.com/images/products/543002/543002_ou_sl.jpg"
        }
    }, ...]
}
```

Parameters:

* `offset` (optional) - defaults to 0
* `limit` (optional) - defaults to 60

## Products details

Example:

```
GET /api/product/$id
HTTP 200
Content-Type: application/json

{
    id: 504815,
    name: "Cutout stretch-jersey dress",
    price: "£1270",
    designer: "Donna Karan",
    onSale: false,
    sizes: [
        {
            id: "00004_S_Clothing",
            name: "S"
        },
        {
            id: "00005_M_Clothing",
         name: "M"
        },
        {
            id: "00006_L_Clothing",
            name: "L"
        },
        {
            id: "00007_XL_Clothing",
            name: "XL"
        }
    ],
    badges: [
        "In_Stock"
    ],
    images: {
        outfit: "//cache.net-a-porter.com/images/products/504815/504815_ou_sl.jpg",
        small: "//cache.net-a-porter.com/images/products/504815/504815_in_sl.jpg",
        large: "//cache.net-a-porter.com/images/products/504815/504815_in_pp.jpg"
    }
}
```
