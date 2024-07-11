# Search a word in a video and get the frames

### This api can be used alongside /api/string-in-all or /api/advanced-search to get the frames where the word appears in the video. It will return the time in seconds where the word appears in the video.


#### URL:
```
/api/string-in-all-paginate-framenumbers
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
- search_string (text, required): The string to be searched.
- video_id (text, required): The video id of the video to be searched.


##### Body Example:

```
{
    "platform": "youtube",
    "video_id": "XcljQpU6dc4",
    "search_string": "client.yaml"
}
```

===


#### Answer 200:
```
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