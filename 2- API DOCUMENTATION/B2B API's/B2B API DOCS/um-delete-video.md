# um-delete-video

## Function to Delete a Video

**Endpoint**: `https://siv.cloudsolute.net/api/um-delete-video`

**Description**: This API is used to delete videos from the server. It requires the video ID and the user ID to verify access rights before deleting the video.

**Method**: POST

**Request Body**:
```
{
    "video_id": "video_id",
    "user_id": "user_id"
}
```

**Parameters**:
- `video_id` (string, required): The ID of the video to be deleted.
- `user_id` (string, required): The ID of the user requesting the deletion.

**Response**:
- **Success (200)**:
```
{
    "message": "Video deleted",
    "result": [],
    "status": 200
}
```

- **Not Having Access to Delete the Video (403)**:
```
{
    "message": "User does not have access to delete the video",
    "result": [],
    "status": 403
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

- **Video Not Found (404)**:
```
{
    "message": "Video not found",
    "result": [],
    "status": 404
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
curl -X POST https://siv.cloudsolute.net/api/um-delete-video \
     -H "Content-Type: application/json" \
     -d '{
           "video_id": "video_id",
           "user_id": "user_id"
         }'
```

**Notes**:
- Ensure that you have the necessary permissions to access this API.
- The `user_id` must be valid and associated with a user who has access to delete the video.
- The `video_id` must be a valid video ID associated with the user.

<!-- For more details, refer to the [complete API documentation](#). -->
