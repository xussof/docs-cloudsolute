# um-get-hls-playlist
## Function to Get the HLS Playlist

**Endpoint**: `https://siv.cloudsolute.net/api/um-get-hls-playlist/{video_id}`

**Description**: This API retrieves the HLS playlist for a specified video.

**Method**: POST

**Request Body**:
```
{
    "user_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.78_vQ1O74ZExEBPedRmWeMLU3UFEe86F_HGv7qQIbaY"
}
```

**Parameters**:
- `video_id` (string, required): The ID of the video for which to retrieve the HLS playlist.
- `user_token` (string, required): The user token for authentication.

**Response**:
- **Success (200)**:
```

#EXTM3U
#EXT-X-VERSION:3
#EXT-X-TARGETDURATION:17
#EXT-X-MEDIA-SEQUENCE:0
#EXT-X-PLAYLIST-TYPE:VOD
#EXTINF:16.666667,
vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0-0.ts
#EXTINF:8.333333,
vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0-1.ts
#EXTINF:8.333333,
vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0-2.ts
#EXTINF:8.333333,
vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0-3.ts
#EXTINF:8.333333,
vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0-4.ts
#EXTINF:16.666667,
vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0-5.ts
#EXTINF:8.333333,
vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0-6.ts
...
#EXTINF:16.666667,
vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0-65.ts
#EXTINF:8.333333,
vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0-66.ts
#EXTINF:8.333333,
vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0-67.ts
#EXTINF:0.533333,
vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0-68.ts
#EXT-X-ENDLIST
```

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

- **Internal Server Error (500)**:
```

{
    "message": "Internal server error",
    "result": [],
    "status": 500
}
```

**Example Usage**:
```
curl -X POST https://siv.cloudsolute.net/api/um-get-hls-playlist/vid-Oh04G9dm5B179LUeR5eBXsViBnufr1nccBREFj77K0 \
     -H "Content-Type: application/json" \
     -d '{
           "user_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.78_vQ1O74ZExEBPedRmWeMLU3UFEe86F_HGv7qQIbaY"
         }'
```

**Notes**:
- Ensure that you have the necessary permissions to access this API.
- The `user_token` must be valid and associated with a user who has access to the specified video.
- The HLS playlist is returned in the standard M3U8 format.


