# Get all info of a video

### Get all stored info such metadata from giving the video id


#### URL:
```
/api/get-all-info-by-vidid
```

#### Method:
```
POST
```

#### Headers:
```
{
    "Content-Type": "application/json",
    "X-RapidAPI-Host": "cloudsolute-prod.p.rapidapi.com",
    "X-RapidAPI-Key": Token generated through API key section.
}
```


#### Body:

=== Body Legend

Mandatory:

- platform (text, required): The platform on which the search operation needs to be performed.
- video_id (text, required): The video id of the video to be searched.


##### Body Example:

```
{
    "platform": "youtube",
    "video_id": "XcljQpU6dc4"
}
```

===


#### Answer 200:
```
{
    "message": "Results found",
    "result": [
        {
            "data": {
                "@timestamp": "2024-03-25T14:24:54.007Z",
                "aspect_ratio": 1.78,
                "captions": [],
                "category": "N/A",
                "channel_id": "@xussof",
                "channel_name": "xussof",
                "comments": 0,
                "dislikes": 0,
                "duration": 6,
                "duration_cv": 0,
                "file_path": "unknown",
                "formats": [
                    "sb0",
                    "233",
                    "234",
                    "139",
                    "140",
                    "251",
                    "269",
                    "160",
                    "230",
                    "134",
                    "18",
                    "605",
                    "22",
                    "232",
                    "136",
                    "270",
                    "137"
                ],
                "fps": 15,
                "fps_cv": 0,
                "frame_type": "initial",
                "height": 1080,
                "likes": 1,
                "platform": "youtube",
                "quality": "1080p",
                "tags": [],
                "thumbnail_url": "https://i.ytimg.com/vi/GQa931EQkOk/maxresdefault.jpg",
                "title": "black",
                "total_frames": 90,
                "total_frames_cv": 0,
                "video_description": "",
                "video_id": "GQa931EQkOk",
                "video_license": "N/A",
                "video_url": "https://www.youtube.com/watch?v=GQa931EQkOk",
                "views": 30,
                "width": 1920
            }
        }
    ],
    "status": 200
}
```

#### Answer 404:
```
{
    "message": "No results found",
    "result": [],
    "status": 404
}
```



#### Answer 500:
```
{
    "message": "Backend request error on api function: name 's' is not defined",
    "result": [],
    "status": 500
}
```