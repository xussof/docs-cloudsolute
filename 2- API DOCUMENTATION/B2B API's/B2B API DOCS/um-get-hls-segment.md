# um-get-hls-segment

## Function to Get the HLS Segment

**Endpoint**: `https://siv.cloudsolute.net/api/um-get-hls-segment/{video_id}/{segment}`

**Description**: This API retrieves a specific HLS segment for a specified video.

**Method**: POST

**Request Body**:
```
{
    "user_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.78_vQ1O74ZExEBPedRmWeMLU3UFEe86F_HGv7qQIbaY"
}
```

**Parameters**:
- `video_id` (string, required): The ID of the video from which to retrieve the HLS segment.
- `segment` (integer, required): The segment number to retrieve.
- `user_token` (string, required): The user token for authentication.

**Response**:
- **Success (200)**:
  - **Content-Type**: `application/octet-stream`
  - **Description**: The response body contains the binary data of the requested HLS segment.


- **Not Owning the Video (403)**:
```
{
    "message": "User has no rights to access the video Error the video is not owned by any company",
    "result": [],
    "status": 403
}
```

- **Invalid Token (401)**:
```
{
    "message": "Invalid or expired user token",
    "result": [],
    "status": 401
}
```

- **Segment Not Found (404)**:
```
{
    "message": "Segment not found",
    "result": [],
    "status": 404
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

**Example Usage**:
curl -X POST https://siv.cloudsolute.net/api/um-get-hls-segment/vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0/1 \
     -H "Content-Type: application/json" \
     -d '{
           "user_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.78_vQ1O74ZExEBPedRmWeMLU3UFEe86F_HGv7qQIbaY"
         }'

**Notes**:
- Ensure that you have the necessary permissions to access this API.
- The `user_token` must be valid and associated with a user who has access to the specified video.
- The response will be binary data representing the HLS segment. Make sure to handle it appropriately in your application.

<!-- For more details, refer to the [complete API documentation](#). -->
