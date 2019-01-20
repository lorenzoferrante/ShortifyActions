---
layout: default
---

[Back](./)

# Documentation

## URL Scheme [BETA]
Shortify Actions supports URL Scheme that enables to add content to it. 

## Base URL
The base URL for Shortify Actions is:
`ShortifyActions2://`

## Paths
There are two paths that are currently supported: `/add` and `/addJSON`

## `/add`
The `/add` path lets you add just one action. To do so, you need to specify 3 parameters:
- `name: String` (must be URL encoded)
- `url: String`
- `collection: String`

The `collection` parameter must be one of these:
- `Tracks`
- `Artists`
- `Albums`
- `Playlists`
- `Videos`
- `Web Links` (must be URL encoded, so `Web%20Links`)

An example callback would be:
```
ShortifyActions2:///add?name=Let%20It%20Be&url=https://www.youtube.com/watch?v=QDYfEBY9NM4&collection=Videos
```

## `/addJSON`
The `/addJSON` path lets you add a collection of items. To use this path, you need to specify one parameters: 
- `items: JSON`

The `items` parameter must be formatted this way:
```JSON
{
    "items": [
        {
            "name": "Example%20Article",
            "url": "https://exampleArticle.com",
            "collection": "Web%20Links"
        },
        ...
    ]
}
```

Note that every item inside `items` has its own `collection` parameter, so you can add items to different collections.

An example callback would be:
```
ShortifyActions2:///items=
{  
   "items":[  
      {  
         "name":"Apple%20Publishes%20Videos%20Showcasing%20iPad%20Pro%20Workflows",
         "url":"https://www.macstories.net/news/apple-publishes-videos-showcasing-ipad-pro-workflows/",
         "collection":"Web%20Links"
      },
      {  
         "name":"Thinking%20Different%3A%20Keys%20to%20Adopting%20an%20iPad-First%20Workflow",
         "url":"https://www.macstories.net/stories/thinking-different-keys-to-adopting-an-ipad-first-workflow/",
         "collection":"Web%20Links"
      }
   ]
}
```
