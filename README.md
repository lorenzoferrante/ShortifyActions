- [Privacy Policy](./privacy.html)
- [Link to Public Beta]()

# Documentation

## URL Scheme
Shortify Actions supports URL Scheme that enables to add content to it. There are two paths that are currently supported,`/add` and `/addJSON`

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
```http
ShortifyActions2:///add?name=Let%20It%20Be&url=https://www.youtube.com/watch?v=QDYfEBY9NM4&collection=Videos
```

## `/addJSON`
