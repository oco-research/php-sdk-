# Garage Week 2021

## Autogenerated JavaScript client oco-research/php-sdk

API version: `1.1.11`

Package version: `1.1.11`

    This is a sample Pet Store Server based on the OpenAPI 3.0 specification.  You can find out more about
Swagger at [http://swagger.io](http://swagger.io). In the third iteration of the pet store, we've switched to the design first approach!
You can now help us improve the API whether it's by making changes to the definition itself or to the code.
That way, with time, we can improve the API in general, and expose some of the new features in OAS3.

Some useful links:
- [The Pet Store repository](https://github.com/swagger-api/swagger-petstore)
- [The source API definition for the Pet Store](https://github.com/swagger-api/swagger-petstore/blob/master/src/main/resources/openapi.yaml)


## Installation & Usage

### Requirements

PHP 7.3 and later.
Should also work with PHP 8.0 but has not been tested.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), run:

```bash
composer require oco-research/php-sdk
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


    
// Configure OAuth2 access token for authorization: petstore_auth
$config = GarageWeek\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new GarageWeek\Api\PetApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$pet = new \GarageWeek\PetStoreClient\Pet(); // \GarageWeek\PetStoreClient\Pet | Create a new pet in the store

try {
    $result = $apiInstance->addPet($pet);
        print_r($result);
    } catch (Exception $e) {
    echo 'Exception when calling PetApi->addPet: ', $e->getMessage(), PHP_EOL;
    }

```

## API Endpoints

To browse the REST API reference and try sending the requests from your browser, see our [REST docs website](https://oco-research.github.io/php-sdk/).

All URIs are relative to *https://petstore3.swagger.io/api/v3*.

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*PetApi* | [**addPet**](docs/Api/PetApi.md#addpet) | **POST** /pet | Add a new pet to the store
*PetApi* | [**deletePet**](docs/Api/PetApi.md#deletepet) | **DELETE** /pet/{petId} | Deletes a pet
*PetApi* | [**findPetsByStatus**](docs/Api/PetApi.md#findpetsbystatus) | **GET** /pet/findByStatus | Finds Pets by status
*PetApi* | [**findPetsByTags**](docs/Api/PetApi.md#findpetsbytags) | **GET** /pet/findByTags | Finds Pets by tags
*PetApi* | [**getPetById**](docs/Api/PetApi.md#getpetbyid) | **GET** /pet/{petId} | Find pet by ID
*PetApi* | [**updatePet**](docs/Api/PetApi.md#updatepet) | **PUT** /pet | Update an existing pet
*PetApi* | [**updatePetWithForm**](docs/Api/PetApi.md#updatepetwithform) | **POST** /pet/{petId} | Updates a pet in the store with form data
*PetApi* | [**uploadFile**](docs/Api/PetApi.md#uploadfile) | **POST** /pet/{petId}/uploadImage | uploads an image
*StoreApi* | [**deleteOrder**](docs/Api/StoreApi.md#deleteorder) | **DELETE** /store/order/{orderId} | Delete purchase order by ID
*StoreApi* | [**getInventory**](docs/Api/StoreApi.md#getinventory) | **GET** /store/inventory | Returns pet inventories by status
*StoreApi* | [**getOrderById**](docs/Api/StoreApi.md#getorderbyid) | **GET** /store/order/{orderId} | Find purchase order by ID
*StoreApi* | [**placeOrder**](docs/Api/StoreApi.md#placeorder) | **POST** /store/order | Place an order for a pet
*UserApi* | [**createUser**](docs/Api/UserApi.md#createuser) | **POST** /user | Create user
*UserApi* | [**createUsersWithListInput**](docs/Api/UserApi.md#createuserswithlistinput) | **POST** /user/createWithList | Creates list of users with given input array
*UserApi* | [**deleteUser**](docs/Api/UserApi.md#deleteuser) | **DELETE** /user/{username} | Delete user
*UserApi* | [**getUserByName**](docs/Api/UserApi.md#getuserbyname) | **GET** /user/{username} | Get user by user name
*UserApi* | [**loginUser**](docs/Api/UserApi.md#loginuser) | **GET** /user/login | Logs user into the system
*UserApi* | [**logoutUser**](docs/Api/UserApi.md#logoutuser) | **GET** /user/logout | Logs out current logged in user session
*UserApi* | [**updateUser**](docs/Api/UserApi.md#updateuser) | **PUT** /user/{username} | Update user

## Models

- [Address](docs/Model/Address.md)
- [ApiResponse](docs/Model/ApiResponse.md)
- [Category](docs/Model/Category.md)
- [Customer](docs/Model/Customer.md)
- [Order](docs/Model/Order.md)
- [Pet](docs/Model/Pet.md)
- [Tag](docs/Model/Tag.md)
- [User](docs/Model/User.md)

## Authorization
    
    ### api_key

        - **Type**: API key
        - **API key parameter name**: api_key
        - **Location**: HTTP header


    
    ### petstore_auth

        - **Type**: `OAuth`
        - **Flow**: `implicit`
        - **Authorization URL**: `https://petstore3.swagger.io/oauth/authorize`
        - **Scopes**: 
            - **write:pets**: modify pets in your account
            - **read:pets**: read your pets

## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```
