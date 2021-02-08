# Module 10: REST

***

## Getting Started

In completing this module you may use 3rd-party libraries to help you accomplish your goals if you wish to do so.

For this module, **create a new Git branch for your Laravel application from Module 9**, and call the branch `rest`.

The link below may provide some valuable insight.

- [Designing a Secure REST (Web) API without OAuth](http://web.archive.org/web/20150908221444/http://www.thebuzzmedia.com/designing-a-secure-rest-api-without-oauth-authentication)
- [HMAC Function In PHP - How To Create A Signature] (https://www.php.net/manual/en/function.hash-hmac.php)

***

## Completing the Module

### Part 1: Integrating a REST API

1. Create a new __resourceful__ controller that obeys proper REST conventions for managing CRUD operations for any model that you already have in your application.  Alternatively, if you'd like you can create a new model for this purpose. We'll refer to this controller as your "API controller".
2. Your API controller should output JSON along with the proper HTTP status code for each request/response. Any responses should contain relevant data about the outcome or condition of the request that was made.

### Part 2: API Authentication

1. Create a new __resourceful__ controller, model and associated views for managing multiple api consumers. Each API consumer should at a minimum have attributes for api_key and shared_secret. You'll use these attributes later to authenticate the API client.

> Most APIs require some sort of query authentication: a method of signing API requests with an API key and signature. The signature is usually generated using a shared secret. This is usually sent over in the Authorization header. When you're consuming an API, there should be easy to follow steps to create signatures so that the API server can authenticate your API requests. When you're writing your own API, you have to create both server-side signature validation and a client-side signature creation strategy.

2. Modify the API controller you created in Part 1 to to handle server-side signature validation of the API request. You'll need to integrate the API consumer records with their key and shared secret attributes that you created in the step above.

### Part 3: An API Client

Create a new Git repo called `rest-client-ex`. In this repo you will create a collection of PHP code which will consume the API you've just created. Use your own judgement on how you'd like to setup this client application. You could make another Laravel app, or even plain PHP files. You be the judge.

1. Create rest-client code that executes each REST endpoint of your API controller. In doing this, you'll need to handle the client-side (API/REST client) signature creation.

***

## Wrapping Up

When you are done, push your code to GitHub. Please create a tag called `v2.0` with a message of `"ready for review"` in both your Laravel app repo and the new `rest-client-ex` repo. Be sure your tags are pushed to the remote repository and are visible in GitHub.

Create an issue titled **Review Module 10 - REST** and assign it to [**@generationtux-helmsmen**](https://github.com/generationtux-helmsmen).
