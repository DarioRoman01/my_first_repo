# API-Desing

{% api-method method="post" host="" path="/albums/createAlbum/" %}
{% api-method-summary %}
Create Album
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allow users to create an album if they have artist status
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="AUTHORIZATION" type="string" required=false %}
Authentication Token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="title" type="string" required=true %}
Album title
{% endapi-method-parameter %}

{% api-method-parameter name="release\_date" type="string" required=true %}
Album release date \(date time\)
{% endapi-method-parameter %}

{% api-method-parameter name="cover\_image" type="object" required=false %}
Album cover image
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "title": "album title",
    "cover_image": "https://image.url",
    "release_date": "2006-10-25 14:30:59",
    "likes": 0
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Authentication token not provide
{% endapi-method-response-example-description %}

```
{"message": "Authentication credentials where not provide"}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
Requesting user has no artist status
{% endapi-method-response-example-description %}

```
{"message": "You do not have permissions to perform this action"}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="/songs/createSong/" %}
{% api-method-summary %}
Create Song
{% endapi-method-summary %}

{% api-method-description %}
this endpoint allows you to create a song only if you have artist status
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="AUTHORIZATION" type="string" required=false %}
Authentication Token 
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="release\_date" type="object" required=true %}
Song release date \(date time\)
{% endapi-method-parameter %}

{% api-method-parameter name="cover\_image" type="object" required=false %}
Song image\(optional\)
{% endapi-method-parameter %}

{% api-method-parameter name="title" type="string" required=true %}
Song title
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Request was successfull
{% endapi-method-response-example-description %}

```
{
    "title": "Awesome Song",
    "cover_image": "https://image.url",
    "release_date": "2006-10-25 14:30:59",
    "likes": 0
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Request has no token authentication
{% endapi-method-response-example-description %}

```
{"message": "Authentication credentials where not provide"}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
Requesting user has no artist status
{% endapi-method-response-example-description %}

```
{"message": "You do not have permissions to perform this action"}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.cakes.com" path="/artist/<pk>/" %}
{% api-method-summary %}
Get artist
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get artist by id
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="pk" type="string" %}
ID of the cake to get, for free of course.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token to track down who is emptying our stocks.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Artist successfully retrieved.
{% endapi-method-response-example-description %}

```
{
    "artist_name": "Awesome Artist",
    "picture": "http://picture.url"
    "followers": "5644"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a artist matching this query.
{% endapi-method-response-example-description %}

```
{    "message": "Detail not found"}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



