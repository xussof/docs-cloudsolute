# string-in-all-paginate-framenumbers-b2b

## API to Search for Frame Numbers with a Specific String in a Given Video

**Endpoint**: `https://siv.cloudsolute.net/api/string-in-all-paginate-framenumbers-b2b`

**Description**: This API is linked to `string-in-all-b2b` and will be called once `string-in-all-b2b` has been called. It searches for frame numbers with a specific string in a given video and paginates the results.

**Method**: POST

**Request Body**:
{
    "video_id": "vid-XcljQpU6dc4",
    "search_string": "import"
}

**Parameters**:
- `video_id` (string, required): The ID of the video in which to search for the string.
- `search_string` (string, required): The word or phrase to search for in the video.

**Response**:
- **Success (200)**:
{
    "message": "Results found",
    "result": [
        {
            "data": [
                {
                    "frame_num": 1
                }
            ]
        }
    ],
    "status": 200
}

- **No Results Found (404)**:
{
    "message": "No results found",
    "result": [],
    "status": 404
}

- **API Error (500)**:
{
    "message": "Backend request error on business function: search_string_on_vidid_get_framenumbers name 's' is not defined",
    "result": [],
    "status": 500
}

**Example Usage**:
curl -X POST https://siv.cloudsolute.net/api/string-in-all-paginate-framenumbers-b2b \
     -H "Content-Type: application/json" \
     -d '{
           "video_id": "vid-XcljQpU6dc4",
           "search_string": "import"
         }'

**Notes**:
- Ensure that you have the necessary permissions to access this API.
- The `search_string` parameter is case-sensitive.
- This API should be called after `string-in-all` to paginate through the results.

<!-- For more details, refer to the [complete API documentation](#). -->
