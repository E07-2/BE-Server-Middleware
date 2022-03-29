# BE-Server-Middleware

This is small exercise to practice writing our custom middleware.

Please create a small Express server that has:

- A `POST` endpoint at `/validateUser`.
- A `POST` endpoint at `/sanitizeUser`.

Both endpoints should be responsible for accepting a JSON object like the following:

```json
{
  "firstName" : "steve",
  "lastName" : "stevenson",
  "age": "129",
  "fbw": "36"
  "profession" : "Musician",
  "favoriteBands" : ["Radiohead", "Motorhead", "Machinehead", "The talking heads" ],
  "email" : "steve@steve.com"
}
```

For the `/validateUser` endpoint

- Create a middleware method that will make sure the object received contains `firstName`, `lastName`, `age`, `fbw` and `email`.
- Create a middleware method that will check if the user is above 18years old
- Create a middleware method that will check if the user belongs to our FBW
- If all the above is true, then you should send a response with a success message
- If any of the middleware fails, you should send a response with an error message that says why the user is not valid.

#### EXAMPLE RESPONSES

```json
// Success case
{
  "message" : "This user is valid!"
}


// Failure
{
  "message": "We can not validate your user. They are not a member of FBW36"
}


// Failure
{
  "message": "We can not validate your user. They are  below 18 years of age"
}

```

For the `/sanitizeUser` endpoint:

- Create a middleware that makes the `firstName` and `lastName` start with a capital letter
- Create a middleware that sorts the `favoriteBands` array alphabetically
- Create a middleware that will turn `age` and `fbw` to numbers

#### EXAMPLE RESPONSES

```json
{
  "firstName" : "Steve",
  "lastName" : "Stevenson",
  "age": 129,
  "fbw": 36
  "profession" : "Musician",
  "favoriteBands" : ["Machinehead","Motorhead", "Radiohead",  "The Talking Heads" ],
  "email" : "steve@steve.com"
}

```
