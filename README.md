# Server Middleware

A small exercise to practice writing custom middleware within an Express.js server

## What you will be doing

You will be creating a server with two endpoints, both of which will be accepting **POST** requests.

Both of these endpoints will be expecting a JSON object with user data.

### Example

```json
{
  "firstName" : "steve",
  "lastName" : "stevenson",
  "age": "129",
  "fbw": "36",
  "profession" : "Musician",
  "favoriteBands" : ["Radiohead", "Motorhead", "Machinehead", "The talking heads" ],
  "email" : "steve@metallica.com"
}
```

The endpoints will then read and process this data.

## Tasks

### Task 1 - Getting ready

1. Initialise npm into your project with `npm init -y`
2. Install the express.js npm package `npm i express`
3. Create the file `server.js`

### Task 2 - Setting up your server

Create your **express.js** server in the `server.js` file

### Task 3 - Creating the validateUser endpoint

Create an endpoint which;

1. Responds to the path `/validateUser`
2. Responds to **POST** request methods

### Task 4 - Creating middleware

1. Create a **middleware function** that checks the object contains **values** for the keys `firstName`, `lastName`, `age`, `fbw` and `email`
2. Create a **middleware function** that will check if the user is above **18** years old
3. If any of the middleware fails, you should send a response with an **error** message that says why the user is not valid

    #### Example failure response
    ```json
    {
      "message": "We can not validate your user. They are  below 18 years of age"
    }
    ```

### Task 5 - Applying the middleware

1. Apply all the middleware you created in **Task 4** to the **validateUser** endpoint

2. If the request passes successfully through the middleware, **validateUser** should send a response with a **success** message

   #### Example success response
    ```json
    {
      "message" : "This user is valid!"
    }
    ```

### Task 6 - Creating the sanitizeUser endpoint

Create an endpoint which;

1. Responds to the path `/sanitizeUser`
2. Responds to **POST** request methods

### Task 7 - Creating middleware

1. Create a **middleware function** that makes the `firstName` and `lastName` start with a capital letter
2. Create a **middleware function** that sorts the `favoriteBands` array alphabetically
3. Create a **middleware function** that will convert `age` and `fbw` to numbers

### Task 8 - Applying the middleware

1. Apply all the middleware you created in **Task 7** to the **sanitizeUser** endpoint

2. If the request passes successfully through the middleware, **sanitizeUser** should send a response with the updated **POST** data

    #### Example response
    
    ```json
    {
      "firstName" : "Steve",
      "lastName" : "Stevenson",
      "age": 129,
      "fbw": 36,
      "profession" : "Musician",
      "favoriteBands" : ["Machinehead", "Motorhead", "Radiohead", "The Talking Heads"],
      "email" : "steve@steve.com"
    }
    ```
