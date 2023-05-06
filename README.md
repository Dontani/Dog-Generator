
Live Demo https://doggenny.netlify.app/
# Dog Generator App

This app provides a random dog name, picture, fun fact, sex, age, dislikes, and likes for a specific dog breed. The data is retrieved from the Dog CEO API, which provides hundreds of dog breeds to choose from.

## Usage

To use the Dog Generator app, simply open the app and choose a dog breed from the list of available breeds. Once you have selected a breed, the app will display the dog's name, picture, fun fact, sex, age, dislikes, and likes.

## Installation

To install the Dog Generator app, follow these steps:

1. Clone the repository to your local machine.
2. Install the required packages by running `npm install`.
3. Start the app by running `npm start`.

## API

The Dog Generator app utilizes the Dog CEO API to retrieve data about dog breeds. To access the API, send a HTTP GET request to the following endpoint:

```
https://dog.ceo/api/breed/<breed_name>/images/random
```

Replace `<breed_name>` with the name of the breed you want to retrieve. The API will return a JSON object containing a random image of the breed.

To retrieve data about a specific dog breed, send a HTTP GET request to the following endpoint:

```
https://example.com/api/dog?breed=<breed_name>
```

Replace `<breed_name>` with the name of the breed you want to retrieve. The breed name should be in lowercase with underscores instead of spaces. The API will return a JSON object containing the following fields:

```
{
  "name": "Buddy",
  "image_url": "https://example.com/images/golden_retriever.jpg",
  "fun_fact": "Golden Retrievers are excellent swimmers and have a natural instinct to retrieve.",
  "sex": "Male",
  "age": "2 years",
  "likes": "Playing fetch, swimming, belly rubs",
  "dislikes": "Loud noises, vacuum cleaners"
}
```

The `name` field provides the name of the dog, the `image_url` field provides a URL for a picture of the dog, the `fun_fact` field provides a random fun fact about the breed, the `sex` field provides the sex of the dog, the `age` field provides the age of the dog, the `likes` field provides the likes of the dog, and the `dislikes` field provides the dislikes of the dog.

If the breed name is not found in the database, the API will return a 404 error with a message "Breed not found."

## Example

To use the Dog Generator app, select a breed from the list of available breeds and click the "Generate" button. The app will display the dog's name, picture, fun fact, sex, age, dislikes, and likes.

To retrieve data from the Dog CEO API using JavaScript, you can use the following code:

```
const breedName = 'golden_retriever';
fetch(`https://dog.ceo/api/breed/${breedName}/images/random`)
  .then(response => response.json())
  .then(data => {
    // Display image
    const image = document.createElement('img');
    image.src = data.message;
    document.getElementById('image-container').appendChild(image);
  })
  .catch(error => console.error(error))

fetch(`https://example.com/api/dog?breed=${breedName}`)
  .then(response => response.json())
  .then(data => {
    // Display name, fun fact, sex, age, likes, and dislikes
    document.getElementById('name').textContent = data.name;
    document.getElementById('fun-fact').textContent = data.fun_fact;
    document
