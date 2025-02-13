# string-in-all-b2b

## Freemium API to Search a Word Over the Entire Video Database

**Endpoint**: `https://siv.cloudsolute.net/api/string-in-all-b2b`

**Description**: This API allows you to search for a specific word across the entire video database. It returns a list of video IDs where the word is found.

**Method**: POST

**Request Body**:
```
{
    "search_string": "import",
    "page_size": 10,
    "offset_page": 0
}
```

**Parameters**:
- `search_string` (string, required): The word or phrase to search for in the video database.
- `page_size` (integer, optional): The number of results to return per page. Default is 10.
- `offset_page` (integer, optional): The page number to retrieve. Default is 0.

**Response**:
- **Success (200)**:
```
{
    "message": "Results found",
    "result": [
        {
            "data": [
                {
                    "id": "vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0"
                },
                {
                    "id": "vid-Oh04G9dm5B179LUesaasssssssaDGDFGDFGDDGDFGF"
                }
            ]
        }
    ],
    "status": 200
}
```

- **No Results Found (404)**:
```
{
    "message": "No results found",
    "result": [],
    "status": 404
}
```

- **API Error (500)**:
```
{
    "message": "Backend request error on api function: name 's' is not defined",
    "result": [],
    "status": 500
}
```

**Example Usage**:
```
curl -X POST https://siv.cloudsolute.net/api/string-in-all-b2b \
     -H "Content-Type: application/json" \
     -d '{
           "search_string": "import",
           "page_size": 10,
           "offset_page": 0
         }'
```

**Notes**:
- Ensure that you have the necessary permissions to access this API.
- The `search_string` parameter is case-sensitive.
- The `page_size` and `offset_page` parameters can be used to paginate through large result sets.

<!-- For more details, refer to the [complete API documentation](#). -->
