# Basic Search

### Freemium Api to search a word over the entire video database


#### URL:
```
/api/string-in-all
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
- page_size (text, required): The number of results to be included in each page.
- offset_page (text, required): The page number for fetching the results.


##### Body Example:

```
{
    "platform": "youtube",
    "search_string": "like",
    "page_size": 10,
    "offset_page": "0"
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