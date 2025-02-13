# um-upload-video

# Function to Upload a Video

**Endpoint**: `https://siv.cloudsolute.net/api/um-upload-video`

**Description**: This API uploads a video file to the server. It auto-generates a unique video ID, uploads the video to the bucket, inserts the video data into the database, and returns the video ID.

**Method**: POST

**Request Body**:
- **Form Data**:
  - `video_file` (file, required): The video file to be uploaded.
  - `user_id` (string, required): The ID of the user uploading the video.

**Example Request**:
```
curl -X POST https://siv.cloudsolute.net/api/um-upload-video \
     -H "Content-Type: multipart/form-data" \
     -F "video_file=@path/to/your/video.mp4" \
     -F "user_id=user_id"
```

**Response**:
- **Success (200)**:
```
{
  "message": "Uploaded video black2.mp4 with video_id vid-BDr8QivUGyHXq0RZL4CzqiEeKDQUWh2IfZjU5Uz3o with size 296.24 KB extension .mp4. And will be fully processed in 1.58 minutes",
  "result": [
    {
      "data": {
        "process_estimation": "1.58 minutes",
        "video_extension": ".mp4",
        "video_id": "vid-BDr8QivUGyHXq0RZL4CzqiEeKDQUWh2IfZjU5Uz3o",
        "video_name": "black2.mp4",
        "video_size": "296.24 KB"
      }
    }
  ],
  "status": 200
}
```

- **Not Having Access to Upload to the Company (403)**:
```
{
    "message": "User does not have access to the company",
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

**Notes**:
- Ensure that you have the necessary permissions to access this API.
- The `video_file` must be a valid video file.
- The `user_id` must be valid and associated with a user who has access to upload videos.
- The response includes details about the uploaded video, such as the unique video ID, size, extension, and estimated processing time.

<!-- For more details, refer to the [complete API documentation](#). -->
