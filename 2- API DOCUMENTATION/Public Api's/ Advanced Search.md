# Advanced Search

### Search for a string in all elk, and returns the vid:id of the videos where the string appears, and paginates the results by 10 by default


#### URL:
```
/api/advanced-search
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

- user_token (string): The user token for authentication.
- page_size (integer): The number of results to be displayed per page.
- offset_page (string): The page number for pagination.
- search_string (string): The keyword for the search.
- platform (string): The platform on which the videos are hosted.

Optionals:

- video_id (string): The unique IDs of the videos to be searched.
- title (string): The title of the videos to be searched.
_ channel_name (string): The name of the channel to be searched.
- tags (string): The tags associated with the videos.
- views (object): An object containing the minimum and maximum number of views for the videos.
    - min (integer): The minimum number of views.
    - max (integer): The maximum number of views.
- comments (object): An object containing the minimum and maximum number of comments for the videos.
    - min (integer): The minimum number of comments.
    - max (integer): The maximum number of comments.
- duration (object): An object containing the minimum and maximum duration of the videos (in seconds).
    - min (integer): The minimum duration of the videos.
    - max (integer): The maximum duration of the videos.

##### Body Example:

```
{
    "user_token": "ey...",
    "page_size": 10,
    "offset_page": “0”,
    "search_string": "history",
    "platform": "youtube",
    "video_id": "XcljQpU6dc4,GQa931EQkOk",
    "title": "black",
    "channel_name": "envatotuts",
    "tags": "html, javascript",
    "views": {
        "min": 0,
        "max": 1000
    },
    "comments": {
        "min": 0,
        "max": 400
    },
    "duration": {
        "min": 150,
        "max": 4000
    }
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
                    "id": "GQa931EQkOk"
                },
                {
                    "id": "XcljQpU6dc4"
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
    "message": "Please authentificate first",
    "result": [],
    "status": 403
}

```

or:

```
{
    "message": "You have no advanced searches left",
    "result": [],
    "status": 403
}
```

#### Answer 500:
```
{
    "message": "Backend request error on business function: insert_data_handler relation \"listss\" does not exist\nLINE 1: INSERT INTO LISTSs (db_list_owner_id, db_list_name, db_list_...\n                    ^\n",
    "result": [],
    "status": 500
}
```