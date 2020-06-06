# Nine and Line API Documentation


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
* `small`,
* `medium`,
* `large`

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

#### Subscriptions
- [Create a subscription](#create-a-subscription)
- [Get a subscription list](#get-a-subscription-list)
- [Get a subscription](#get-a-subscription)
- [Delete a subscription](#delete-a-subscription)
- [Get a subscription item list](#get-a-subscription-item-list)
- [Get a subscription item](#get-a-subscription-item)
- [Delete a subscription item](#delete-a-subscription-item)

#### Veterinarians
- [Create a veterinarian](#create-a-veterinarian)
- [Get a veterinarian list](#get-a-veterinarian-list)
- [Get a veterinarian](#get-a-veterinarian)
- [Update a veterinarian](#update-a-veterinarian)
- [Delete a veterinarian](#delete-a-veterinarian)



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
* `404` if address does not exist


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
* `404` if address does not exist


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
* The `payment_method` will be generated through stripe. 


**Body:**
```json
{
    "pet_id": 1,
    "variant_id": 32090941521998
}
```

**Response:**
```json
{
    "id": 2254450819150,
    "customer_id": 3135862145102,
    "line_items": [
        {
            "id": 4942931394638,
            "order_id": 2254450819150,
            "product_id": 4590007091278,
            "title": "GI Bland - Chicken",
            "variant_id": 32090941521998,
            "variant_title": "10",
            "price": 40.0,
            "quantity": 1,
            "requires_shipping": true
        }
    ],
    "order_number": 1025,
    "note": null,
    "tags": null,
    "subtotal_price": 40.0,
    "total_discounts": 0.0,
    "total_tax": 0.0,
    "total_price": 40.0,
    "currency": "USD",
    "financial_status": "paid",
    "fulfillment_status": null,
    "order_status_url": null,
    "cancel_reason": null,
    "cancelled_at": null,
    "closed_at": null,
    "processing_method": "",
    "processed_at": "2020-05-07T20:18:03.000000",
    "is_active": true,
    "created_at": "2020-05-08T00:18:04.730348",
    "updated_at": "2020-05-08T00:18:04.730352"
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
        "id": 2254450819150,
        "customer_id": 3135862145102,
        "line_items": [
            {
                "id": 4942931394638,
                "order_id": 2254450819150,
                "product_id": 4590007091278,
                "title": "GI Bland - Chicken",
                "variant_id": 32090941521998,
                "variant_title": "10",
                "price": 40.0,
                "quantity": 1,
                "requires_shipping": true
            }
        ],
        "order_number": 1025,
        "note": null,
        "tags": null,
        "subtotal_price": 40.0,
        "total_discounts": 0.0,
        "total_tax": 0.0,
        "total_price": 40.0,
        "currency": "USD",
        "financial_status": "paid",
        "fulfillment_status": null,
        "order_status_url": null,
        "cancel_reason": null,
        "cancelled_at": null,
        "closed_at": null,
        "processing_method": "",
        "processed_at": "2020-05-07T20:18:03.000000",
        "is_active": true,
        "created_at": "2020-05-08T00:18:04.730348",
        "updated_at": "2020-05-08T00:18:04.730352"
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
/v1/order/:id
```

**Response:**
```json
{
    "id": 2254450819150,
    "customer_id": 3135862145102,
    "line_items": [
        {
            "id": 4942931394638,
            "order_id": 2254450819150,
            "product_id": 4590007091278,
            "title": "GI Bland - Chicken",
            "variant_id": 32090941521998,
            "variant_title": "10",
            "price": 40.0,
            "quantity": 1,
            "requires_shipping": true
        }
    ],
    "order_number": 1025,
    "note": null,
    "tags": null,
    "subtotal_price": 40.0,
    "total_discounts": 0.0,
    "total_tax": 0.0,
    "total_price": 40.0,
    "currency": "USD",
    "financial_status": "paid",
    "fulfillment_status": null,
    "order_status_url": null,
    "cancel_reason": null,
    "cancelled_at": null,
    "closed_at": null,
    "processing_method": "",
    "processed_at": "2020-05-07T20:18:03.000000",
    "is_active": true,
    "created_at": "2020-05-08T00:18:04.730348",
    "updated_at": "2020-05-08T00:18:04.730352"
}
```

**Status Codes:**
* `200` if successful
* `401` if invalid credentials
* `404` if pet does not exist


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
/v1/pet/:id
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
* `404` if pet does not exist


### Update a pet

**PATCH:**
```
/v1/pet/:id
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
/v1/pet/:id
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
* `pet-type`: value must either be `canine` or `feline` 
* `tag`: a canine or feline health tag (multiple tags can exist)

Example: `/v1/product?tag=obesity&tag=cancer&tag=diabetes&pet-type=feline`


**Notes:**
* Returns all products (unsorted) if no query params are specified 
* If tags are provided, the product list will be sorted according to our ranking system

**Response:**
```json
[
    {
        "id": 4590004666446,
        "title": "Advanced Kidney Care",
        "product_type": "canine",
        "images": [
            {
                "id": 14641723080782,
                "position": 1,
                "width": 263,
                "height": 242,
                "src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_f8d62422-5aee-465e-8f79-7b486a2df200.png?v=1587916342",
                "created_at": "2020-04-26T15:52:22.000000",
                "updated_at": "2020-04-26T15:52:22.000000"
            }
        ],
        "is_prescribed": true,
        "created_at": "2020-03-17T23:32:10.000000",
        "updated_at": "2020-05-27T01:17:06.000000"
    },
    {
        "id": 4590009942094,
        "title": "Allergy Care - Kangaroo",
        "product_type": "feline",
        "images": [
            {
                "id": 14641710071886,
                "position": 1,
                "width": 536,
                "height": 540,
                "src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/example_diet_a723a3f7-1dd4-488a-9bce-ef2609c5cd45.png?v=1587916170",
                "created_at": "2020-04-26T15:49:30.000000",
                "updated_at": "2020-04-26T15:49:30.000000"
            }
        ],
        "is_prescribed": true,
        "created_at": "2020-03-17T23:49:30.000000",
        "updated_at": "2020-05-27T00:28:36.000000"
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
    "images": [
        {
            "id": 14641723080782,
            "position": 1,
            "width": 263,
            "height": 242,
            "src": "https://cdn.shopify.com/s/files/1/0279/8229/9214/products/canine_diet_f8d62422-5aee-465e-8f79-7b486a2df200.png?v=1587916342",
            "created_at": "2020-04-26T15:52:22.000000",
            "updated_at": "2020-04-26T15:52:22.000000"
        }
    ],
    "is_prescribed": true,
    "created_at": "2020-03-17T23:32:10.000000",
    "updated_at": "2020-05-27T01:17:06.000000",
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
* `404` if product not found


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


### Create a subscription

**POST:**
```
/v1/subscription
```

**Notes:**
* This route will create a customer subscription through stripe


**Body:**
```json
{
    "line_items": [
        {
            "pet_id": 1,
            "variant_id": 32204998606926
        }
    ]
}
```

**Response:**
```json
{
    "id": 1,
    "customer_id": 3224454660174,
    "cancel_at_period_end": false,
    "current_period_start": "2020-06-06T00:42:10.000000",
    "current_period_end": "2020-06-20T00:42:10.000000",
    "items": [
        {
            "id": 1,
            "subscription_id": 1,
            "pet_name": "Luna",
            "variant_id": 32204998606926,
            "product": "Advanced Kidney Care",
            "amount": 45.96,
            "currency": "usd",
            "interval": "week",
            "interval_count": 2,
            "is_active": false,
            "created_at": "2020-06-06T00:42:11.778116",
            "updated_at": "2020-06-06T00:42:11.778123"
        }
    ],
    "status": "canceled",
    "created_at": "2020-06-06T00:42:11.778685",
    "updated_at": "2020-06-06T00:44:03.141234"
}
```

**Status Codes:**
* `201` if successful
* `400` if incorrect data provided
* `401` if invalid credentials
* `409` if a pet already has a subscription


### Get a subscription list

**GET:**
```
/v1/subscription
```

**Response:**
```json
[
    {
        "id": 1,
        "customer_id": 3224454660174,
        "cancel_at_period_end": false,
        "current_period_start": "2020-06-06T00:42:10.000000",
        "current_period_end": "2020-06-20T00:42:10.000000",
        "items": [
            {
                "id": 1,
                "subscription_id": 1,
                "pet_name": "Luna",
                "variant_id": 32204998606926,
                "product": "Advanced Kidney Care",
                "amount": 45.96,
                "currency": "usd",
                "interval": "week",
                "interval_count": 2,
                "is_active": false,
                "created_at": "2020-06-06T00:42:11.778116",
                "updated_at": "2020-06-06T00:42:11.778123"
            }
        ],
        "status": "canceled",
        "created_at": "2020-06-06T00:42:11.778685",
        "updated_at": "2020-06-06T00:44:03.141234"
    },
    ...
]
```

**Status Codes:**
* `200` if successful
* `401` if invalid credentials


### Get a subscription

**GET:**
```
/v1/subscription/:subscription_id
```

**Response:**
```json
{
    "id": 1,
    "customer_id": 3224454660174,
    "cancel_at_period_end": false,
    "current_period_start": "2020-06-06T00:42:10.000000",
    "current_period_end": "2020-06-20T00:42:10.000000",
    "items": [
        {
            "id": 1,
            "subscription_id": 1,
            "pet_name": "Luna",
            "variant_id": 32204998606926,
            "product": "Advanced Kidney Care",
            "amount": 45.96,
            "currency": "usd",
            "interval": "week",
            "interval_count": 2,
            "is_active": false,
            "created_at": "2020-06-06T00:42:11.778116",
            "updated_at": "2020-06-06T00:42:11.778123"
        }
    ],
    "status": "canceled",
    "created_at": "2020-06-06T00:42:11.778685",
    "updated_at": "2020-06-06T00:44:03.141234"
}
```

**Status Codes:**
* `200` if successful
* `401` if invalid credentials
* `404` if it does not exist


### Delete a subscription

**DELETE:**
```
/v1/subscription/:subscription_id
```

**Notes:**
* This route will cancel a customer's subscription and including all subscription items in it.
If a customer wants to cancel only one item the [Delete a subscription item](#delete-a-subscription-item)
route should be used instead.

**Response:** None

**Status Codes:**
* `204` if successful
* `401` if invalid credentials
* `404` if does not exist


### Get a subscription item list

**GET:**
```
/v1/subscription/:subscription_id/item
```

**Response:**
```json
[
    {
        "id": 1,
        "subscription_id": 1,
        "pet_name": "Luna",
        "variant_id": 32204998606926,
        "product": "Advanced Kidney Care",
        "amount": 45.96,
        "currency": "usd",
        "interval": "week",
        "interval_count": 2,
        "is_active": false,
        "created_at": "2020-06-06T00:42:11.778116",
        "updated_at": "2020-06-06T00:42:11.778123"
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
/v1/subscription/:subscription_id/item/:subscription_item_id
```

**Response:**
```json
{
    "id": 1,
    "subscription_id": 1,
    "pet_name": "Luna",
    "variant_id": 32204998606926,
    "product": "Advanced Kidney Care",
    "amount": 45.96,
    "currency": "usd",
    "interval": "week",
    "interval_count": 2,
    "is_active": false,
    "created_at": "2020-06-06T00:42:11.778116",
    "updated_at": "2020-06-06T00:42:11.778123"
}
```

**Status Codes:**
* `200` if successful
* `401` if invalid credentials
* `404` if it does not exist


### Delete a subscription item

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
* `404` if veterinarian does not exist


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
