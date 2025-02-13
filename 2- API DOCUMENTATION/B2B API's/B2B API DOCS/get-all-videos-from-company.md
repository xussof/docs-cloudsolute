# get-all-videos-from-company

## Function to Retrieve All Videos from a Company

**Endpoint**: `https://siv.cloudsolute.net/api/get-all-videos-from-company`

**Description**: This API retrieves all videos associated with a company using the authentication mechanism.

**Method**: POST

**Request Body**:
```
{
    "user_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..EXbJqu6Gfn8LJ22c5aaD0kI_vHe_lkOHYQLBxGspV2s",
    "page_size": 100,
    "offset_page": "0"
}
```

**Parameters**:
- `user_token` (string, required): The user token for authentication.
- `page_size` (integer, optional): The number of results to return per page. Default is 100.
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
                    "id": "vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0",
                    "platform": "cloudsolute"
                },
                {
                    "id": "vid-WtSv5aPqtZhmlzmjg5ORzhngHqT7K3xKDXbBhCmk",
                    "platform": "cloudsolute"
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

- **Invalid Token (401)**:
```
{
    "message": "Token Invalid",
    "result": [],
    "status": 401
}
```

- **Bad Request (400)**:
```
{
    "message": "Missing or invalid parameters",
    "result": [],
    "status": 400
}
```

- **Internal Server Error (500)**:
```
{
    "message": "Internal server error",
    "result": [],
    "status": 500
}
```

**Example Request**:
```
curl -X POST https://siv.cloudsolute.net/api/get-all-videos-from-company \
     -H "Content-Type: application/json" \
     -d '{
           "user_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..EXbJqu6Gfn8LJ22c5aaD0kI_vHe_lkOHYQLBxGspV2s",
           "page_size": 100,
           "offset_page": "0"
         }'
```

**Notes**:
- Ensure that you have the necessary permissions to access this API.
- The `user_token` must be valid and associated with a user who has access to the company's videos.
- The response includes a list of video IDs and their associated platforms.

<!-- For more details, refer to the [complete API documentation](#). -->
