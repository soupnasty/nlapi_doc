# Nine and Line API Documentation


## A Falcon Seed Project

Nine and Line API uses Falcon, a web microframework written in Python. "Falcon follows the REST architectural style, 
meaning (among other things) that you think in terms of resources and state transitions, 
which map to HTTP verbs." - [http://falconframework.org/](http://falconframework.org/)

* [https://github.com/falconry/falcon](https://github.com/falconry/falcon)
* [http://falcon.readthedocs.org/en/latest/](http://falcon.readthedocs.org/en/latest/)


## Table of Contents

- [Admin Sequence Diagram](#admin-sequence-diagram)
- [User Sequence Diagram](#user-sequence-diagram)
- [Nine and Line Classifications](#nine-and-line-classifications)
- [API Routes](#api-routes)


### Admin Sequence Diagram
![Admin Sequence Diagram](http://www.plantuml.com/plantuml/png/ZP71JiGW48RlF0KlOBnxCBl6usOl7ZnFONJ9Ka0OedrxST9CR7PRUYpvFlZpzL08CjNHAp0KipxQqGKrn1_zTed9VKpAHE_Ha8kXw7SS4dnYKQb9phW4WHWy9gSi40nGa0zUvm-5mUfs7LzvFhs0kRQJXNy-BUppwSPLl4e_FCi0_QJ1MaqPWHwjGz8fHriDAI4QFIzhy2seJQvMP_ogM4ZDv2p9-gNPq3o9ik1M7XEbf9OF_pyZExV6tMeSwxxpZSCbngjYX5afULyeKp2BNfoviRc5nooS1OBrVn3p7pj2gE3zjD9Vm1t5cTiTM-X-PncnMPQ9JancklsOwjGpjL0SzmKKjjzGqBqPHTXTKeoDc09rUWhMIoeWLpsqmphwNm00)


### User Sequence Diagram
![User Sequence Diagram](http://www.plantuml.com/plantuml/png/ZPInZjim38PtFOLUeEYUeKYBZaMNehYPbfb4Y2Ff93evl_rHFaCnOSNG5DZwIFty4kQO22ADjq618H_r_uHHTVv3_xluO4-JCduOq93rBkatx0ASCQd0DTRO08vcy6UmgWU23XBEBtul3mfThxdTtFBldrzWhlncNSzlrzNykAdDcVIt7-LwVT1tcomb_S2EFr6L4wQMF0p1I1TqV17a-3hY-uY9r08mAw9omPWlOYXE0Yw4w2xW5DWFbjOohCnHfRE4qjH41CBlWpzRbqUyU7zLcLXGcRZmOs29gDFaZ12IzJ4QMIV6hme6GTMyKcwbVMIoAbKG3KPdkb6feFUTYXWxGWMthrAGLOSICTwTRBnLBKBV9nsGj7KdN_gKM8VvpCInBqxgaJ8ctJsFIpV15HLy99s9InTeE-7o8odPNqvtHy9e7SJfnP0ChfY6OLTqoymItnrTq3iAnA9i9gp_3U5ZbjLRf5Jxfiz8Js1ZG6YzWnsW6r3mCgRSnGorhoB3xPl8SECYCjcoXuorhI63krieaBA5HtJzU1i-0G00)


### Nine and Line Classifications

#### Pet Types
* `canine`,
* `feline`

#### Gender Types
* `male`,
* `female`

#### Canine Activity Levels
* `low`,
* `medium`,
* `high`,
* `extreme`

#### Canine Body Levels
* `very_small`,
* `small`,
* `medium`,
* `large`,
* `very_large`

#### Canine General Conditions
* `poor_hair_coat`,
* `poor_appetite`,
* `diarrhea`,
* `vomiting`,
* `obesity`

#### Canine Medical Conditions
* `kidney_disease_early`,
* `kidney_disease_advanced`,
* `protein_losing_nephropathy`,
* `liver_disease`,
* `pancreatitis`,
* `food_allergy`,
* `inflammatory_bowel_disease`,
* `protein losing_enteropathy`,
* `urinary_stones_calcium_oxalate`,
* `urinary_stones_struvite`,
* `urinary_stones_urate`,
* `diabetes`,
* `heart_disease`,
* `cancer`

#### Canine Living Environment
* `mostly_indoors`,
* `mostly_outdoors`,
* `both`

#### Feline Activity Levels
* `low`,
* `medium`,
* `high`

#### Feline Body Levels
* `very_small`,
* `small`,
* `medium`,
* `large`,
* `very_large`

#### Feline General Conditions
* `poor_hair_coat`,
* `poor_appetite`,
* `diarrhea`,
* `vomiting`,
* `obesity`

#### Feline Medical Conditions
* `kidney_disease_early`,
* `kidney_disease_advanced`,
* `food_allergy`,
* `inflammatory_bowel_disease`,
* `feline_cystitis`,
* `urinary_stones_calcium_oxalate`,
* `urinary_stones_struvite`,
* `diabetes`,
* `heart_disease`,
* `cancer`,

#### Feline Living Environment
* `mostly_indoors`,
* `mostly_outdoors`,
* `both`


### API Routes

For authentication required routes, an Authorization header must be included in the request.
The Authorization header must be the token of signed in customer. A status code of `401` will be returned
for any route that is accessed without proper Authorization. 

#### Customer
- [Check email availability](#check-email-availability)
- [Authenticate a customer](#authenticate-a-customer)
- [Create a customer](#create-a-customer)
- [Get a customer](#get-a-customer)
- [Update a customer](#update-a-customer)
- [Delete a customer](#delete-a-customer)
- [Create a customer address](#create-a-customer-address)
- [Get a customer address list](#get-a-customer-address-list)
- [Get a customer address](#get-a-customer-address)
- [Update a customer address](#update-a-customer-address)
- [Add a customer payment method](#add-a-customer-payment-method)

#### Diet Approval
- [Create a diet approval](#create-a-diet-approval)
- [Get a diet approval list](#get-a-diet-approval-list)
- [Get a diet approval](#get-a-diet-approval)
- [Delete a diet approval](#delete-a-diet-approval)

#### Mailing
- [Add to mailing list](#add-to-mailing-list)

#### Orders
- [Create an order](#create-an-order)
- [Get an order list](#get-an-order-list)
- [Get an order](#get-an-order)

#### Pets
- [Create a pet](#create-a-pet)
- [Get a pet list](#get-a-pet-list)
- [Get a pet](#get-a-pet)
- [Update a pet](#update-a-pet)
- [Delete a pet](#delete-a-pet)
- [Get breed list](#get-pet-breed-list)
- [Get general conditions list](#get-general-conditions-list)
- [Get medical conditions list](#get-medical-conditions-list)

#### Products
- [Get a product list](#get-a-product-list)
- [Get a product detail](#get-a-product-detail)
- [Get a list of product variants](#get-a-list-of-product-variants)
- [Get product recommendations](#get-product-recommendations)

#### Subscriptions
- [Create a subscription](#create-a-subscription)
- [Get a subscription item list](#get-a-subscription-item-list)
- [Get a subscription item](#get-a-subscription-item)
- [Cancel a subscription item](#cancel-a-subscription-item)

#### Veterinarians
- [Create a veterinarian](#create-a-veterinarian)
- [Get a veterinarian list](#get-a-veterinarian-list)
- [Get a veterinarian](#get-a-veterinarian)
- [Update a veterinarian](#update-a-veterinarian)
- [Delete a veterinarian](#delete-a-veterinarian)


## Customer Routes

### Check email availability

**POST:**
```
/v1/email-availability
```

**Body:**
```json
{
    "email": "something@email.com"
}
```

**Response:** None

**Status Codes:**
* `200` if email is available
* `400` if incorrect data provided
* `409` if email is in use


### Authenticate a customer

**POST:**
```
/v1/authenticate
```

**Body:**
```json
{
    "email": "something@email.com",
    "password": "12345678"
}
```

**Response:**
```json
{
    "id": 1,
    "token": "reallylongjsonwebtokenstring"
}
```

**Status Codes:**
* `200` if successful
* `400` if incorrect data provided
* `401` if invalid credentials


### Create a customer

**POST:**
```
/v1/customer
```

**Notes:**
* An auth `token` will be returned with the newly created customer. One will need to set this as the Authorization 
header for auth required HTTPS requests. For future auth tokens, use the `/v1/authenticate` route. 


**Body:**
```json
{
    "first_name": "Tony",
    "last_name": "Stark",
    "email": "ironman@starktech.com",
    "password": "12345678"
}
```

**Response:**
```json
{
    "id": 1,
    "token": "reallylongjsonwebtokenstring"
}
```

**Status Codes:**
* `201` if successful
* `400` if incorrect data provided
* `409` if email is in use


### Get a customer

**GET:**
```
/v1/customer
```

**Notes:**
* Grab the customer info for the current signed in user


**Response:**
```json
{
    "id": 3163908669518,
    "email": "ironman@starktech.com",
    "first_name": "Tony",
    "last_name": "Stark",
    "state": "disabled",
    "phone": "317-908-5555",
    "currency": "USD",
    "note": null,
    "tags": "",
    "orders_count": 1,
    "total_spent": 40.0,
    "verified_email": true,
    "verified_payment_method": true,
    "accepts_marketing": false,
    "is_active": true,
    "created_at": "2020-05-16T16:31:49.323423",
    "updated_at": "2020-05-17T21:01:04.000000"
}
```

**Status Codes:**
* `200` if successful
* `401` if invalid credentials


### Update a customer

**PATCH:**
```
/v1/customer
```

**Body:**
```json
{
    "phone": "555-555-5555"
}
```

**Response:**
```json
{
    "id": 3163908669518,
    "email": "ironman@starktech.com",
    "first_name": "Tony",
    "last_name": "Stark",
    "state": "disabled",
    "phone": "555-555-5555",
    "currency": "USD",
    "note": null,
    "tags": "",
    "orders_count": 1,
    "total_spent": 40.0,
    "verified_email": true,
    "verified_payment_method": true,
    "accepts_marketing": false,
    "is_active": true,
    "created_at": "2020-05-16T16:31:49.323423",
    "updated_at": "2020-05-17T21:01:04.000000"
}
```

**Status Codes:**
* `200` if successful
* `400` if incorrect data provided
* `401` if invalid credentials


### Delete a customer

**DELETE:**
```
/v1/customer
```

**Response:** None

**Status Codes:**
* `204` if successful
* `401` if invalid credentials
* `404` if does not exist


### Create a customer address

**POST:**
```
/v1/customer/address
```

**Notes:**
* The `default` field may only be true. Setting one address to the default will automatically set all others to false. 


**Body:**
```json
{
    "first_name": "Tony",
    "last_name": "Stark",
    "address1": "123 w iron lane.",
    "address2": "apt 5",
    "city": "Chicago",
    "province": "Illinois",
    "country": "United States",
    "zip": "60613",
    "default": true
}
```

**Response:**
```json
{
    "id": 3358804901966,
    "customer_id": 3167348686926,
    "first_name": "Tony",
    "last_name": "Stark",
    "address1": "123 w iron lane.",
    "address2": "apt 5",
    "city": "Chicago",
    "zip": "60613",
    "province": "Illinois",
    "province_code": "IL",
    "country": "United States",
    "country_code": "US",
    "default": true
}
```

**Status Codes:**
* `200` if successful
* `400` if incorrect data provided
* `401` if invalid credentials


### Get a customer address list

**GET:**
```
/v1/customer/address
```

**Response:**
```json
[
    {
        "id": 3358804901966,
        "customer_id": 3167348686926,
        "first_name": "Tony",
        "last_name": "Stark",
        "address1": "123 w iron lane.",
        "address2": "apt 5",
        "city": "Chicago",
        "zip": "60613",
        "province": "Illinois",
        "province_code": "IL",
        "country": "United States",
        "country_code": "US",
        "default": true
    },
    {
        "id": 3358860116046,
        "customer_id": 3167348686926,
        "first_name": "Tony",
        "last_name": "Stark",
        "address1": "456 w iron lane.",
        "address2": "apt 6",
        "city": "Chicago",
        "zip": "60613",
        "province": "Illinois",
        "province_code": "IL",
        "country": "United States",
        "country_code": "US",
        "default": false
    }
]
```

**Status Codes:**
* `200` if successful
* `400` if incorrect data provided
* `401` if invalid credentials


### Get a customer address

**GET:**
```
/v1/customer/address/:address_id
```

**Response:**
```json
{
    "id": 3358804901966,
    "customer_id": 3167348686926,
    "first_name": "Tony",
    "last_name": "Stark",
    "address1": "123 w iron lane.",
    "address2": "apt 5",
    "city": "Chicago",
    "zip": "60613",
    "province": "Illinois",
    "province_code": "IL",
    "country": "United States",
    "country_code": "US",
    "default": true
}
```

**Status Codes:**
* `200` if successful
* `401` if invalid credentials
* `404` if does not exist


### Update a customer address

**PATCH:**
```
/v1/customer/address/:address_id
```

**Body:**
```json
{
    "address1": "1000 New Lane"
}
```

**Response:**
```json
{
    "id": 3358804901966,
    "customer_id": 3167348686926,
    "first_name": "Tony",
    "last_name": "Stark",
    "address1": "1000 New Lane",
    "address2": "apt 5",
    "city": "Chicago",
    "zip": "60613",
    "province": "Illinois",
    "province_code": "IL",
    "country": "United States",
    "country_code": "US",
    "default": true
}
```

**Status Codes:**
* `200` if successful
* `400` if incorrect data provided
* `401` if invalid credentials
* `404` if does not exist


### Add a customer payment method

**POST:**
```
/v1/customer/payment-method
```

**Body:**
```json
{
    "payment_method": "pm_card_visa"
}
```

**Response:** None

**Status Codes:**
* `200` if successful
* `400` if incorrect data provided
* `409` stripe issue


## Diet Approval Routes

### Create a diet approval

**POST:**
```
/v1/diet-approval
```

**Notes:**
* This route will create a veterinarian diet approval form for the veterinarian and send it to them.
* Only call this route for therapeutic diets.


**Body:**
```json
{
	"line_item_id": 5119807946830,
	"veterinarian_id": 1
}
```

**Response:**
```json
{
    "id": 44,
    "customer_id": 3224454660174,
    "pet_id": 1,
    "veterinarian_id": 1,
    "line_item_id": 5119807946830,
    "status": "open",
    "signed_at": null,
    "created_at": "2020-06-07T19:23:29.157002",
    "updated_at": "2020-06-07T19:23:29.157004"
}
```

**Status Codes:**
* `200` if successful
* `400` if incorrect data provided or diet is non-therapeutic
* `401` if invalid credentials
* `409` if customer data is missing
0


### Get a diet approval list

**GET:**
```
/v1/diet-approval
```

**Response:**
```json
[
    {
        "id": 44,
        "customer_id": 3224454660174,
        "pet_id": 1,
        "veterinarian_id": 1,
        "line_item_id": 5119807946830,
        "status": "open",
        "signed_at": null,
        "created_at": "2020-06-07T19:23:29.157002",
        "updated_at": "2020-06-07T19:23:29.157004"
     },
    ...
]
```

**Status Codes:**
* `200` if successful
* `401` if invalid credentials


### Get a diet approval

**GET:**
```
/v1/diet-approval/:diet_approval_id
```

**Response:**
```json

{
    "id": 44,
    "customer_id": 3224454660174,
    "pet_id": 1,
    "veterinarian_id": 1,
    "line_item_id": 5119807946830,
    "status": "open",
    "signed_at": null,
    "created_at": "2020-06-07T19:23:29.157002",
    "updated_at": "2020-06-07T19:23:29.157004"
 }
```

**Status Codes:**
* `200` if successful
* `401` if invalid credentials


### Delete a diet approval

**DELETE:**
```
/v1/diet_approval/:diet_approval_id
```

**Response:** None

**Status Codes:**
* `204` if successful
* `401` if invalid credentials
* `404` if does not exist


## Mailing List Routes

### Add to mailing list

**POST:**
```
/v1/mailing/subscribe
```

**Body:**
```json
{
    "email": "someemail@gmail.com"
}
```

**Response:**
```json
{
    "email": "someemail@gmail.com",
    "created_at": "2020-01-11T21:26:11.913263"
}
```

**Status Codes:**
* `201` if successful
* `400` if incorrect data provided
* `409` if email is already subscribed


### Create an order

**POST:**
```
/v1/order
```

**Notes:**
* This route will take a paid subscription and create a Shopify order to be processed


**Body:**
```json
{
	"subscription_id": 660517636861735
}
```

**Response:**
```json
{
    "id": 2456682463310,
    "customer_id": 3341083181134,
    "line_items": [
        {
            "id": 5331236749390,
            "order_id": 2456682463310,
            "product": {
                "id": 4590004666446,
                "title": "Advanced Kidney Care",
                "product_type": "canine",
                "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_f8d62422-5aee-465e-8f79-7b486a2df200.png?v=1587916342",
                "is_prescription": true,
                "created_at": "2020-03-17T23:32:10.000000",
                "updated_at": "2020-07-18T10:29:16.000000"
            },
            "variant": {
                "id": 32204975833166,
                "title": "40",
                "price": 64.49,
                "weight": 0.0,
                "weight_unit": "lb",
                "created_at": "2020-05-18T16:45:24.000000",
                "updated_at": "2020-05-18T16:47:26.000000"
            },
            "price": 64.49,
            "quantity": 1
        },
        {
            "id": 5331236782158,
            "order_id": 2456682463310,
            "product": {
                "id": 4590005649486,
                "title": "Allergy Care - Kangaroo",
                "product_type": "canine",
                "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_d2ded379-ae3c-456d-9328-18d8cf52e72a.png?v=1587916360",
                "is_prescription": true,
                "created_at": "2020-03-17T23:36:02.000000",
                "updated_at": "2020-07-18T10:29:31.000000"
            },
            "variant": {
                "id": 32205011419214,
                "title": "40",
                "price": 64.49,
                "weight": 0.0,
                "weight_unit": "lb",
                "created_at": "2020-05-18T16:58:49.000000",
                "updated_at": "2020-05-18T16:58:49.000000"
            },
            "price": 64.49,
            "quantity": 1
        }
    ],
    "order_number": 1038,
    "note": null,
    "tags": null,
    "subtotal_price": 128.98,
    "total_tax": 0.0,
    "total_price": 128.98,
    "currency": "USD",
    "financial_status": "paid",
    "fulfillment_status": null,
    "order_status_url": null,
    "cancel_reason": null,
    "cancelled_at": null,
    "closed_at": null,
    "processing_method": "",
    "processed_at": "2020-07-18T07:07:43.000000",
    "created_at": "2020-07-18T11:07:43.796555",
    "updated_at": "2020-07-18T11:07:43.796559"
}
```

**Status Codes:**
* `201` if successful
* `400` if incorrect data provided
* `401` if invalid credentials


### Get an order list

**GET:**
```
/v1/order
```

**Response:**
```json
[
    {
        "id": 2456682463310,
        "customer_id": 3341083181134,
        "line_items": [
            {
                "id": 5331236749390,
                "order_id": 2456682463310,
                "product": {
                    "id": 4590004666446,
                    "title": "Advanced Kidney Care",
                    "product_type": "canine",
                    "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_f8d62422-5aee-465e-8f79-7b486a2df200.png?v=1587916342",
                    "is_prescription": true,
                    "created_at": "2020-03-17T23:32:10.000000",
                    "updated_at": "2020-07-18T11:10:49.000000"
                },
                "variant": {
                    "id": 32204975833166,
                    "title": "40",
                    "price": 64.49,
                    "weight": 0.0,
                    "weight_unit": "lb",
                    "created_at": "2020-05-18T16:45:24.000000",
                    "updated_at": "2020-05-18T16:47:26.000000"
                },
                "price": 64.49,
                "quantity": 1
            },
            {
                "id": 5331236782158,
                "order_id": 2456682463310,
                "product": {
                    "id": 4590005649486,
                    "title": "Allergy Care - Kangaroo",
                    "product_type": "canine",
                    "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_d2ded379-ae3c-456d-9328-18d8cf52e72a.png?v=1587916360",
                    "is_prescription": true,
                    "created_at": "2020-03-17T23:36:02.000000",
                    "updated_at": "2020-07-18T11:10:49.000000"
                },
                "variant": {
                    "id": 32205011419214,
                    "title": "40",
                    "price": 64.49,
                    "weight": 0.0,
                    "weight_unit": "lb",
                    "created_at": "2020-05-18T16:58:49.000000",
                    "updated_at": "2020-05-18T16:58:49.000000"
                },
                "price": 64.49,
                "quantity": 1
            }
        ],
        "order_number": 1038,
        "note": null,
        "tags": null,
        "subtotal_price": 128.98,
        "total_tax": 0.0,
        "total_price": 128.98,
        "currency": "USD",
        "financial_status": "paid",
        "fulfillment_status": null,
        "order_status_url": null,
        "cancel_reason": null,
        "cancelled_at": null,
        "closed_at": null,
        "processing_method": "",
        "processed_at": "2020-07-18T07:07:43.000000",
        "created_at": "2020-07-18T11:07:43.796555",
        "updated_at": "2020-07-18T11:07:43.796559"
    },
    ...
]
```

**Status Codes:**
* `200` if successful
* `400` if query params are not integers
* `401` if invalid credentials


### Get an order

**GET:**
```
/v1/order/:order_id
```

**Response:**
```json
{
    "id": 2456682463310,
    "customer_id": 3341083181134,
    "line_items": [
        {
            "id": 5331236749390,
            "order_id": 2456682463310,
            "product": {
                "id": 4590004666446,
                "title": "Advanced Kidney Care",
                "product_type": "canine",
                "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_f8d62422-5aee-465e-8f79-7b486a2df200.png?v=1587916342",
                "is_prescription": true,
                "created_at": "2020-03-17T23:32:10.000000",
                "updated_at": "2020-07-18T11:10:49.000000"
            },
            "variant": {
                "id": 32204975833166,
                "title": "40",
                "price": 64.49,
                "weight": 0.0,
                "weight_unit": "lb",
                "created_at": "2020-05-18T16:45:24.000000",
                "updated_at": "2020-05-18T16:47:26.000000"
            },
            "price": 64.49,
            "quantity": 1
        },
        {
            "id": 5331236782158,
            "order_id": 2456682463310,
            "product": {
                "id": 4590005649486,
                "title": "Allergy Care - Kangaroo",
                "product_type": "canine",
                "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_d2ded379-ae3c-456d-9328-18d8cf52e72a.png?v=1587916360",
                "is_prescription": true,
                "created_at": "2020-03-17T23:36:02.000000",
                "updated_at": "2020-07-18T11:10:49.000000"
            },
            "variant": {
                "id": 32205011419214,
                "title": "40",
                "price": 64.49,
                "weight": 0.0,
                "weight_unit": "lb",
                "created_at": "2020-05-18T16:58:49.000000",
                "updated_at": "2020-05-18T16:58:49.000000"
            },
            "price": 64.49,
            "quantity": 1
        }
    ],
    "order_number": 1038,
    "note": null,
    "tags": null,
    "subtotal_price": 128.98,
    "total_tax": 0.0,
    "total_price": 128.98,
    "currency": "USD",
    "financial_status": "paid",
    "fulfillment_status": null,
    "order_status_url": null,
    "cancel_reason": null,
    "cancelled_at": null,
    "closed_at": null,
    "processing_method": "",
    "processed_at": "2020-07-18T07:07:43.000000",
    "created_at": "2020-07-18T11:07:43.796555",
    "updated_at": "2020-07-18T11:07:43.796559"
}
```

**Status Codes:**
* `200` if successful
* `401` if invalid credentials
* `404` if does not exist


### Create a pet

**POST:**
```
/v1/pet
```

**Notes:**
* The `other_tags` field is optional and should contain tags that are not listed in `general` or `medical` conditions.

**Body:**
```json
{
    "name": "Zino",
    "pet_type": "feline",
    "gender": "female",
    "breed": "",
    "weight": 10,
    "age": 7,
    "activity_level": "low",
    "body_level": "very large",
    "living_environment": "mostly indoors",
    "health_tags": ["obesity", "kidney_disease_early"],
    "other_tags": ["depression"],
    "is_neutered": true
}
```

**Response:**
```json
{
    "id": 8,
    "name": "Zino",
    "pet_type": "feline",
    "gender": "female",
    "breed": "",
    "weight": 10,
    "age": 7,
    "activity_level": "low",
    "body_level": "very large",
    "living_environment": "mostly indoors",
    "health_tags": ["obesity", "kidney_disease_early"],
    "other_tags": ["depression"],
    "is_neutered": true,
    "created_at": "2020-01-11T21:26:11.913263",
    "updated_at": "2020-01-11T21:26:11.913341"
}
```

**Status Codes:**
* `201` if successful
* `400` if incorrect data provided
* `401` if invalid credentials


### Get a pet list

**GET:**
```
/v1/pet
```

**Response:**
```json
[
    {
        "id": 1,
        "name": "Zino",
        "pet_type": "feline",
        "gender": "female",
        "breed": "",
        "weight": 10,
        "age": 7,
        "activity_level": "low",
        "body_level": "very large",
        "living_environment": "mostly indoors",
        "health_tags": ["obesity", "kidney_disease_early"],
        "other_tags": ["depression"],
        "is_neutered": true,
        "created_at": "2020-01-11T21:31:59.925759",
        "updated_at": "2020-01-11T21:31:59.925848"
    },
    {
        "id": 2,
        "name": "Luna",
        "pet_type": "feline",
        "gender": "female",
        "breed": "",
        "weight": 8,
        "age": 5,
        "activity_level": "high",
        "body_level": "small",
        "living_environment": "mostly indoors",
        "health_tags": [],
        "other_tags": [],
        "is_neutered": true,
        "created_at": "2020-01-11T21:31:59.925759",
        "updated_at": "2020-01-11T21:31:59.925848"
    }
]
```

**Status Codes:**
* `200` if successful
* `400` if query params are not integers
* `401` if invalid credentials


### Get a pet

**GET:**
```
/v1/pet/:pet_id
```

**Response:**
```json
{
    "id": 1,
    "name": "Zino",
    "pet_type": "feline",
    "gender": "female",
    "breed": "",
    "weight": 10,
    "age": 8,
    "activity_level": "low",
    "body_level": "very large",
    "living_environment": "mostly indoors",
    "health_tags": ["obesity", "kidney_disease_early"],
    "other_tags": ["depression"],
    "is_neutered": true,
    "created_at": "2020-01-11T21:31:59.925759",
    "updated_at": "2020-01-11T21:31:59.925848"
}
```

**Status Codes:**
* `200` if successful
* `401` if invalid credentials
* `404` if does not exist


### Update a pet

**PATCH:**
```
/v1/pet/:pet_id
```

**Body:**
```json
{
    "activity_level": "low",
}
```

**Response:**
```json
{
    "id": 1,
    "name": "Zino",
    "pet_type": "feline",
    "gender": "female",
    "breed": "",
    "weight": 10,
    "age": 7,
    "activity_level": "low",
    "body_level": "very large",
    "living_environment": "mostly indoors",
    "health_tags": ["obesity", "kidney_disease_early"],
    "other_tags": ["depression"],
    "is_neutered": true,
    "created_at": "2020-01-11T21:31:59.925759",
    "updated_at": "2020-01-11T21:31:59.925848"
}
```

**Status Codes:**
* `200` if successful
* `400` if invalid data
* `401` if invalid credentials
* `404` if does not exist


### Delete a pet

**DELETE:**
```
/v1/pet/:pet_id
```

**Response:** None

**Status Codes:**
* `204` if successful
* `401` if invalid credentials
* `404` if does not exist


### Get pet breed list

**GET:**
```
/v1/pet/info/:pet_type/breeds
```

**Response:**
```json
[
    "abyssinian cat",
    "aegean cat",
    "american curl",
    "american bobtail",
    "american shorthair",
    "american wirehair",
    "arabian mau ",
    "australian mist",
    ...
]
```

**Status Codes:**
* `200` if successful
* `400` if incorrect pet type


### Get general conditions list

**GET:**
```
/v1/pet/info/:pet_type/general-conditions
```

**Response:**
```json
[
    "poor_hair_coat",
    "poor_appetite",
    "diarrhea",
    "vomiting",
    "obesity"
]
```

**Status Codes:**
* `200` if successful
* `400` if incorrect pet type


### Get medical conditions list

**GET:**
```
/v1/pet/info/:pet_type/medical-conditions
```

**Response:**
```json
[
    "kidney_disease_early",
    "kidney_disease_advanced",
    "protein_losing_nephropathy",
    "liver_disease",
    "pancreatitis",
    ...
]
```

**Status Codes:**
* `200` if successful
* `400` if incorrect pet type


### Get a product list

**GET:**
```
/v1/product
```

**Query Params:**
* `product-type`: the options are the same as `pet_type`, must either be `canine` or `feline` 

Example: `/v1/product?product-type=feline`


**Response:**
```json
[
    {
        "id": 4490930159694,
        "title": "Allergy Care - White Fish & Sweet Potato",
        "product_type": "canine",
        "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_797a2cb7-b020-4532-b1f5-3fffc8968fb6.png?v=1587916371",
        "is_prescription": false,
        "created_at": "2020-01-04T19:00:21.000000",
        "updated_at": "2020-07-12T19:51:35.000000"
    },
    {
        "id": 4590004666446,
        "title": "Advanced Kidney Care",
        "product_type": "canine",
        "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_f8d62422-5aee-465e-8f79-7b486a2df200.png?v=1587916342",
        "is_prescription": true,
        "created_at": "2020-03-17T23:32:10.000000",
        "updated_at": "2020-07-12T19:51:58.000000"
    },
    ...
]
```

**Status Codes:**
* `200` if successful
* `400` if query params are not correct type


### Get a product detail

**GET:**
```
/v1/product/:product_id
```

**Response:**
```json
{
    "id": 4590004666446,
    "title": "Advanced Kidney Care",
    "product_type": "canine",
    "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_f8d62422-5aee-465e-8f79-7b486a2df200.png?v=1587916342",
    "is_prescription": true,
    "created_at": "2020-03-17T23:32:10.000000",
    "updated_at": "2020-07-18T11:10:49.000000",
    "general_description": "A diet low in protein, phosphorus, and sodium to help support dogs with advanced (IRIS Stage 3-4) kidney disease.",
    "key_features": [
        "Restricted in protein, phosphorus, and sodium",
        "High-quality protein, providing essential amino acids for the maintenance of strong muscle mass",
        "Enriched in vitamin E and omega-3 fatty acids (EPA/DHA/DPA)",
        "Recommended best for advanced kidney disease (IRIS Stage 3-4), protein losing kidney disease (PLN), and heart disease",
        "Completely balanced for long term feeding under veterinary supervision",
        "No preservatives"
    ],
    "ingredients": "Dark Meat Chicken, Chicken Liver, White Rice, Olive Oil, Carrots, Cauliflower, Kale + Premium Fish Oil, Vitamin & Mineral Supplements",
    "nutrition_facts": {
        "crude_protein": [
            "5.9% (min)",
            "16.5%"
        ],
        "crude_fat": [
            "5.0% (min)",
            "14.0%"
        ],
        "crude_fiber": [
            "0.1% (max)",
            "0.18%"
        ],
        "moisture": [
            "64.5% (max)",
            null
        ],
        "phosphorous": [
            null,
            "0.25%"
        ],
        "sodium": [
            null,
            "0.14%"
        ],
        "potassium": [
            null,
            "0.52%"
        ]
    },
    "nutritional_adequacy_statement": "Advanced Kidney Care Diet is intended for management of advanced kidney diseases.  Use under direct instruction or supervision of a veterinarian."
}
```

**Status Codes:**
* `200` if successful
* `400` if query params are not correct type
* `404` if not found


### Get a list of product variants

**GET:**
```
/v1/product/:product_id/variant
```

**Query Params:**
* `weight`: integer, the weight of the pet in lbs

Example: `/v1/product/4590004666446/variant?weight=10`


**Notes:**
* The `weight` query param is needed in order to select the corresponding variant for the pet. 
* If `weight` is not specified, all product variants will be returned. 

**Response:**
```json
[
    {
        "id": 32204975734862,
        "title": "10",
        "price": 36.49,
        "weight": 0.0,
        "weight_unit": "lb",
        "created_at": "2020-05-18T16:45:24.000000",
        "updated_at": "2020-05-18T16:47:58.000000"
    },
    {
        "id": 32204975767630,
        "title": "20",
        "price": 45.49,
        "weight": 0.0,
        "weight_unit": "lb",
        "created_at": "2020-05-18T16:45:24.000000",
        "updated_at": "2020-05-18T16:47:26.000000"
    },
    ...
]
```

**Status Codes:**
* `200` if successful
* `400` if query params are not correct type


### Get product recommendations

**GET:**
```
/v1/product/recommendation/:product_type
```

**Query Params:**
* `general`: a canine or feline general condition 
* `medical`: a canine or feline medical condition

Example: `/v1/product/recommendation/canine?general=vomiting&general=diarrhea&medical=cancer`


**Notes:**
* The `product_type` must either be `canine` or `feline` 
* The response will contain two sorted lists, `recommendations` and `alternatives`. 

**Response:**
```json
{
    "recommendations": [
        {
            "id": 4590005649486,
            "title": "Allergy Care - Kangaroo",
            "product_type": "canine",
            "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_d2ded379-ae3c-456d-9328-18d8cf52e72a.png?v=1587916360",
            "is_prescription": true,
            "created_at": "2020-03-17T23:36:02.000000",
            "updated_at": "2020-07-10T21:54:26.000000"
        },
        ...
    ],
    "alternatives": [
        {
            "id": 4490930159694,
            "title": "Allergy Care - White Fish & Sweet Potato",
            "product_type": "canine",
            "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_797a2cb7-b020-4532-b1f5-3fffc8968fb6.png?v=1587916371",
            "is_prescription": false,
            "created_at": "2020-01-04T19:00:21.000000",
            "updated_at": "2020-07-12T19:51:35.000000"
        },
        ...
    ]
}
```


### Create a subscription

**POST:**
```
/v1/subscription
```

**Notes:**
* A pet cannot have an existing active subscription 
* Multiple line items with the same `pet_id` are not allowed.
* A customer must have a `payment_method` added 


**Body:**
```json
{
	"items": [
		{
			"pet_id": 2,
			"variant_id": 32204975833166
		},
		{
			"pet_id": 3,
			"variant_id": 32205011419214
		}
	]
}
```

**Response:**
```json
{
    "id": 660517636861735,
    "customer_id": 3341083181134,
    "cancel_at_period_end": false,
    "current_period_start": "2020-07-18T11:07:11.000000",
    "current_period_end": "2020-08-01T11:07:11.000000",
    "items": [
        {
            "id": 129177802981270,
            "subscription_id": 660517636861735,
            "pet_name": "Gordo",
            "product": {
                "id": 4590004666446,
                "title": "Advanced Kidney Care",
                "product_type": "canine",
                "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_f8d62422-5aee-465e-8f79-7b486a2df200.png?v=1587916342",
                "is_prescription": true,
                "created_at": "2020-03-17T23:32:10.000000",
                "updated_at": "2020-07-18T10:29:16.000000"
            },
            "amount": 64.49,
            "currency": "usd",
            "interval": "week",
            "interval_count": 2,
            "quantity": 1,
            "cancel_at_period_end": false,
            "current_period_start": "2020-07-18T11:07:11.000000",
            "current_period_end": "2020-08-01T11:07:11.000000",
            "is_active": true,
            "created_at": "2020-07-18T11:07:12.714361",
            "updated_at": "2020-07-18T11:07:12.714369"
        },
        {
            "id": 548021379723503,
            "subscription_id": 660517636861735,
            "pet_name": "Tony",
            "product": {
                "id": 4590005649486,
                "title": "Allergy Care - Kangaroo",
                "product_type": "canine",
                "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_d2ded379-ae3c-456d-9328-18d8cf52e72a.png?v=1587916360",
                "is_prescription": true,
                "created_at": "2020-03-17T23:36:02.000000",
                "updated_at": "2020-07-18T10:29:31.000000"
            },
            "amount": 64.49,
            "currency": "usd",
            "interval": "week",
            "interval_count": 2,
            "quantity": 1,
            "cancel_at_period_end": false,
            "current_period_start": "2020-07-18T11:07:11.000000",
            "current_period_end": "2020-08-01T11:07:11.000000",
            "is_active": true,
            "created_at": "2020-07-18T11:07:12.714837",
            "updated_at": "2020-07-18T11:07:12.714840"
        }
    ],
    "status": "active",
    "is_active": true,
    "created_at": "2020-07-18T11:07:12.715114",
    "updated_at": "2020-07-18T11:07:12.715116"
}
```

**Status Codes:**
* `201` if successful
* `400` if incorrect data provided
* `401` if invalid credentials
* `409` if a pet already has a subscription


### Get a subscription item list

**GET:**
```
/v1/subscription-item
```

**Response:**
```json
[
    {
        "id": 548021379723503,
        "subscription_id": 660517636861735,
        "pet_name": "Tony",
        "product": {
            "id": 4590005649486,
            "title": "Allergy Care - Kangaroo",
            "product_type": "canine",
            "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_d2ded379-ae3c-456d-9328-18d8cf52e72a.png?v=1587916360",
            "is_prescription": true,
            "created_at": "2020-03-17T23:36:02.000000",
            "updated_at": "2020-07-18T11:10:49.000000"
        },
        "amount": 64.49,
        "currency": "usd",
        "interval": "week",
        "interval_count": 2,
        "quantity": 1,
        "cancel_at_period_end": false,
        "current_period_start": "2020-07-18T11:07:11.000000",
        "current_period_end": "2020-08-01T11:07:11.000000",
        "is_active": true,
        "created_at": "2020-07-18T11:07:12.714837",
        "updated_at": "2020-07-18T11:07:12.714840"
    },
    {
        "id": 129177802981270,
        "subscription_id": 660517636861735,
        "pet_name": "Gordo",
        "product": {
            "id": 4590004666446,
            "title": "Advanced Kidney Care",
            "product_type": "canine",
            "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_f8d62422-5aee-465e-8f79-7b486a2df200.png?v=1587916342",
            "is_prescription": true,
            "created_at": "2020-03-17T23:32:10.000000",
            "updated_at": "2020-07-18T11:10:49.000000"
        },
        "amount": 64.49,
        "currency": "usd",
        "interval": "week",
        "interval_count": 2,
        "quantity": 1,
        "cancel_at_period_end": false,
        "current_period_start": "2020-07-18T11:07:11.000000",
        "current_period_end": "2020-08-01T11:07:11.000000",
        "is_active": true,
        "created_at": "2020-07-18T11:07:12.714361",
        "updated_at": "2020-07-18T11:07:12.714369"
    },
    ...
]
```

**Status Codes:**
* `200` if successful
* `401` if invalid credentials


### Get a subscription item

**GET:**
```
/v1/subscription-item/:subscription_item_id
```

**Response:**
```json
{
    "id": 548021379723503,
    "subscription_id": 660517636861735,
    "pet_name": "Tony",
    "product": {
        "id": 4590005649486,
        "title": "Allergy Care - Kangaroo",
        "product_type": "canine",
        "image_src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_d2ded379-ae3c-456d-9328-18d8cf52e72a.png?v=1587916360",
        "is_prescription": true,
        "created_at": "2020-03-17T23:36:02.000000",
        "updated_at": "2020-07-18T11:10:49.000000"
    },
    "amount": 64.49,
    "currency": "usd",
    "interval": "week",
    "interval_count": 2,
    "quantity": 1,
    "cancel_at_period_end": false,
    "current_period_start": "2020-07-18T11:07:11.000000",
    "current_period_end": "2020-08-01T11:07:11.000000",
    "is_active": true,
    "created_at": "2020-07-18T11:07:12.714837",
    "updated_at": "2020-07-18T11:07:12.714840"
}
```

**Status Codes:**
* `200` if successful
* `401` if invalid credentials
* `404` if does not exist


### Cancel a subscription item

**DELETE:**
```
/v1/subscription/:subscription_id/item/:subscription_item_id
```

**Notes:**
* This route will cancel a specific item in a customer's subscription. If the last remaining active item
is canceled, this will terminate the subscription automatically. 

**Response:** None

**Status Codes:**
* `204` if successful
* `401` if invalid credentials
* `404` if does not exist


### Create a veterinarian

**POST:**
```
/v1/veterinarian
```

**Body:**
```json
{
    "clinic": "Veterinarian Health Clinic",
    "first_name": "John",
    "last_name": "Doe",
    "phone": "555-555-5555",
    "email": "some-email@gmail.com"
}
```

**Response:**
```json
{
    "id": 1,
    "clinic": "Veterinarian Health Clinic",
    "first_name": "John",
    "last_name": "Doe",
    "phone": "555-555-5555",
    "email": "some-email@gmail.com",
    "created_at": "2020-01-11T22:31:05.998866",
    "updated_at": "2020-01-11T22:31:05.999015"
}
```

**Status Codes:**
* `201` if successful
* `400` if incorrect data provided
* `401` if invalid credentials


### Get a veterinarian list

**GET:**
```
/v1/veterinarian
```

**Response:**
```json
[
    {
        "id": 1,
        "clinic": "Veterinarian Health Clinic",
        "first_name": "John",
        "last_name": "Doe",
        "phone": "555-555-5555",
        "email": "some-email@gmail.com",
        "created_at": "2020-01-11T22:31:05.998866",
        "updated_at": "2020-01-11T22:31:05.999015"
    }
]
```

**Status Codes:**
* `200` if successful
* `400` if query params are not integers
* `401` if invalid credentials


### Get a veterinarian

**GET:**
```
/v1/veterinarian/:veterinarian_id
```

**Response:**
```json
{
    "id": 1,
    "clinic": "Veterinarian Health Clinic",
    "first_name": "John",
    "last_name": "Doe",
    "phone": "555-555-5555",
    "email": "some-email@gmail.com",
    "created_at": "2020-01-11T22:31:05.998866",
    "updated_at": "2020-01-11T22:31:05.999015"
}
```

**Status Codes:**
* `200` if successful
* `401` if invalid credentials
* `404` if does not exist


### Update a veterinarian

**PATCH:**
```
/v1/veterinarian/:veterinarian_id
```

**Body:**
```json
{
    "phone": "123-456-7890"
}
```

**Response:**
```json
{
    "id": 1,
    "clinic": "Veterinarian Health Clinic",
    "first_name": "John",
    "last_name": "Doe",
    "phone": "123-456-7890",
    "email": "some-email@gmail.com",
    "created_at": "2020-01-11T22:31:05.998866",
    "updated_at": "2020-01-11T22:31:05.999015"
}
```

**Status Codes:**
* `200` if successful
* `400` if invalid data
* `401` if invalid credentials
* `404` if does not exist


### Delete a veterinarian

**DELETE:**
```
/v1/veterinarian/:veterinarian_id
```

**Response:** None

**Status Codes:**
* `204` if successful
* `401` if invalid credentials
* `404` if does not exist
