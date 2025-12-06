## API overview

This API information is a collection of data for movies, tv-shows, and youtube urls. The actors biography and many other useful information are included. This API provide a complete and updated data information for over 9 milloion movie titles and and 11 million actors / crew and cast members.

## API version

The current version for this API is version one(1).

## Available Endpoints

# Titles
./title: returns array of titles according to filters or sorting query parameter provided.
./x/titles-by-ids: returns array of titles according to array of id's provided.
./titles/{id}: returns title acording to filters / sorting query parameters provided.
./titles/{id}/ratings: returns title rating and votes number.
./titles/series/{id}:  returns array of episodes only with episode id, episode number and season number in ascending order.
./titles/seasons/{id}: returns number of seasons for the series (integer).
./titles/series/{id}/{season}: returns array of episodes only with episode id, season number and episode number (only of the season provided in path).
./titles/episode/{id}: returns episode according to filters / sorting query parameters provided.
./titles/x/upcoming: returns array of upcoming titles according to filters / sorting query parameters provided.

# Search
/titles/search/keyword/{keyword}: retruns an array of titles according to sorting param and the keyword provided in path
/titles/search/title/{title}: returns an array of titles according to filter
/titles/search/akas/{akas}: returns an array of titles according to filters an the aka provided in path, works for exact matches.

# Actors
/actors: returns array of actors accoring to filters provided
/actors/{id}: returns actors details.

# Utils
/title/utils/titleType: returns array of title types
/title/utils/titleType: returns array of genres
/title/utils/lists: returns array of lists (for 'list' query parameter).

 ## Request and Response Format 
 Example of request format using Axios:

 const axios = require('axios');

const options = {
  method: 'GET',
  url: 'https://moviesdatabase.p.rapidapi.com/titles/%7Bid%7D/main_actors',
  headers: {
    'x-rapidapi-key': 'Sign Up for Key',
    'x-rapidapi-host': 'moviesdatabase.p.rapidapi.com'
  }
};

async function fetchData() {
	try {
		const response = await axios.request(options);
		console.log(response.data);
	} catch (error) {
		console.error(error);
	}
}

fetchData();

Example of Response:
Status: 200
Media Type: JSON

## Authentication
Auth. allows clients to have access to request for data information using API key, headers requirment.

## Error Handling
Common error response:
const user = await fetchUser();

console.log(user.username);  // Works
console.log(user.phone);     // ❌ Error: Property 'phone' does not exist

How to handle them in your code.
catch (err) {
        if (axios.isAxiosError(err)) {
          // Axios-specific error handling
          setError(err.response?.data.message || err.message);
        } else {
          // General error handling
          setError('An unexpected error occurred');
        }
      }

 ## Usage Limits and Best Practices 
 # Basic
 Requests: 500,000 / Month       Hard Limit.
 Rate Limit: 1000 requests per hour.
 Bandwidth Platform: 10240MB
 # usage recommendations for effective use of the API.
Clients should go for relevant information first to avoid exceeding the daily limits.







