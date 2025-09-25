# alx-project-0x14

## API Overview
The MoviesDatabase API provides a rich collection of information about movies, TV shows, actors, and crew members. It includes details such as YouTube trailer URLs, awards, biographies, and other valuable metadata. The API contains complete and updated data for:

9+ million titles (movies, series, and episodes)

11+ million actors, crew, and cast members

This makes it a powerful resource for building movie discovery applications, recommendation systems, or entertainment dashboards.

## API Version
v1

## Available Endpoints
/titles – Retrieve movie and series titles with filters (e.g., year, genre, sorting).

/titles/search/title – Search for titles by name.

/titles/x/titles-by-ids – Fetch multiple titles by their IDs.

/titles/x/upcoming – Get a list of upcoming titles.

/actors – Retrieve actor details, including biography and filmography.

/actors/search – Search actors by name.

## Request and Response Format
# Example Request
GET https://moviesdatabase.p.rapidapi.com/titles?year=2024&limit=10&page=1
Headers:
  x-rapidapi-host: moviesdatabase.p.rapidapi.com
  x-rapidapi-key: YOUR_API_KEY

# Example Response
{
  "results": [
    {
      "id": "tt1234567",
      "titleText": {
        "text": "Example Movie"
      },
      "releaseYear": {
        "year": "2024"
      },
      "primaryImage": {
        "url": "https://example.com/poster.jpg"
      }
    }
  ]
}

## Authentication Requirements
All requests require an API key. You must include the following headers:

x-rapidapi-host: moviesdatabase.p.rapidapi.com  
x-rapidapi-key: YOUR_API_KEY


You can obtain your API key by subscribing to the MoviesDatabase API on RapidAP

## Error Handling
400 Bad Request – Invalid query parameters.

401 Unauthorized – Missing or invalid API key.

404 Not Found – Resource not found.

429 Too Many Requests – Rate limit exceeded.

500 Internal Server Error – Problem with the API server.

Always check response.ok in your code and handle errors gracefully.

## Usage Limits and Best Practices
Rate Limits: Requests are limited based on your RapidAPI subscription plan.

Best Practices:

Cache frequently used data to avoid unnecessary API calls.

Use pagination (page and limit parameters) when fetching large datasets.

Handle error responses with retries or fallbacks.

Keep your API key secure (store in environment variables, not in source code).
