# alx-project-0x14
 The project focuses on creating a responsive, well-structured web application built with Next.js, TypeScript and Tailwind CSS with proper API integration which allows users to browse movies from the MoviesDatabase API, view movie details, and search for films by year or genre.


## API Overview
The MoviesDatabase API provides access to data on over 9 million movies, TV series, and episodes—including ratings, cast, plots, images, and more.

## Version
v1

## Available Endpoints
- `GET /search/movie` – Search for movies by title  
- `GET /search/tv` – Search for TV shows by name  
- `GET /movies/{id}` – Get movie details  
- `GET /series/{id}` – Get TV series details  
- `GET /movies/{id}/cast` – Retrieve cast and crew  
- `GET /movies/{id}/similar` – Suggested titles (if available)

## Request and Response Format
Requests are made over HTTPS; responses are in JSON.  
Example:
```http
GET /search/movie?query=Inception&page=1
Authorization: Bearer YOUR_API_KEY
```
Response:
```json
{
  "page": 1,
  "total_results": 205,
  "results": [
    {
      "id": 27205,
      "title": "Inception",
      "release_year": 2010,
      "overview": "A thief who steals corporate secrets …",
      "poster_url": "https://…",
      "rating": 8.8
    }
  ]
}
```

## Authentication
Include an API key:
- In header: `Authorization: Bearer YOUR_API_KEY`  
- Or as query parameter: `api_key=YOUR_API_KEY`  

## Error Handling
Handle these responses:
- 401 Unauthorized – invalid API key  
- 400 Bad Request – missing or incorrect parameters  
- 404 Not Found – no matching record  
- 429 Too Many Requests – exceeded rate limit  
Each error includes a JSON `status_code` and `status_message`.

## Usage Limits and Best Practices
- Respect rate limits and implement retry/back‑off logic  
- Use pagination to manage large result sets  
- Cache results to minimize repeated calls  
- Apply filtering to reduce payload and improve performance  
- Adhere to API usage policies and avoid misuse
