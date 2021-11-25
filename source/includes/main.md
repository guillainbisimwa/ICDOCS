---
noteId: "3cfeda904e0911ecaf3d2117c19ffd22"
tags: []
---

# Introduction to Instagram clone API

Welcome to the Zaio API doc. You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```javascript
import { kittn } from "kittn";

const api = kittn.authorize("meowmeowmeow");
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](https://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class=notice>
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Photo

## Get All pictures

Here, you **can** fetch all pictures

### HTTP REQUEST

`GET: www.test.com/photo`

You must have a token to make your request!
After authentification you must have it!

`Token: **********************************`

Read more how to add [token](https://developer.mozilla.org/fr/docs/Web/API/Fetch_API)

### Parametre

| Params | type   | Description   |
| ------ | ------ | ------------- |
| token  | string | An Auth token |

> To call the GET HTTP request you must use this code sample

```javascript
import axios from "axios";
// Make a request for a user with a given ID
axios
  .get("www.test.com/photo")
  .then(function (response) {
    // handle success
    console.log(response);
  })
  .catch(function (error) {
    // handle error
    console.log(error);
  })
  .then(function () {
    // always executed
  });
```

> Above you have a response from the server in JSON Formated

```json
[
  {
    "id": 1,
    "url": "www.amazone.com/kjsgkjajdgf",
    "timeline": "2021-01-01",
    "user": "fhshlshlhvklhslkdhvsd"
  }
]
```

<aside class="success">
   Remember, if GET pictures successfully you are gonna have a JSON formated answer
</aside>

<aside class="error">
  You will gaona have an empty array if you forget to put a good token
</aside>

## Get one picture

## Like a picture

## Delete a picture

# Activities

## Get All activites

```javascript
import { kittn } from "kittn";

const api = kittn.authorize("meowmeowmeow");
const kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET https://example.com/api/kittens`

### Query Parameters

| Parameter    | Default | Description                                                                      |
| ------------ | ------- | -------------------------------------------------------------------------------- |
| include_cats | false   | If set to true, the result will also include cats.                               |
| available    | true    | If set to false, the result will include kittens that have already been adopted. |

<aside class=success>
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```javascript
import { kittn } from "kittn";

const api = kittn.authorize("meowmeowmeow");
const max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class=warning>
Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.
</aside>

### HTTP Request (with ID)

`GET https://example.com/kittens/<ID>`

### URL Parameters

| Parameter | Description                      |
| --------- | -------------------------------- |
| ID        | The ID of the kitten to retrieve |
