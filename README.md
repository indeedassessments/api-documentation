# Indeed Assessments API

**WARNING: THE API IS STILL UNDER CONSTRUCTION AND SOME RESPONSES AND
RESOURCE URLS MIGHT CHANGE IN THE NEAR FUTURE.**

Welcome to the Indeed Assessments API. If you're looking to integrate your
application with Indeed Assessments or create your own application in concert
with data inside of Indeed Assessments, you're in the right place. We're happy
to have you!


## Compatibility with previous APIs

The Indeed Assessments API is not compatible with the [Interviewed
API](https://github.com/prehire/interviewed-api). All integrations will start 
fresh with the new API. The core ingredients are the same, though: Indeed
Assessments is a REST-style API that uses JSON for serialization.


## Making a request

All URLs start with **`https://api.indeed-assessments.com/v1/`**. URLs are
HTTPS only. The latest version of the API is `v1`.

To make a request for all the bundles in your account, append the `bundles`
index path to the base URL to form something like
`https://api.indeed-assessments.com/v1/bundles.json`. In cURL, it looks like
this:

```bash
curl -H "X-IndeedAssessmentsToken: $API_KEY" \
  https://api.indeed-assessments.com/v1/bundles.json
```

To create something, you also have to include the `Content-Type` header and the
JSON data:

```bash
curl -H "X-IndeedAssessmentsToken: $API_KEY" \
  -H 'Content-Type: application/json' \
  -d '{ "name": "My new bundle!" }' \
  https://api.indeed-assessments.com/v1/bundles.json
```

Throughout the Indeed Assessments API docs, we include "Copy as cURL" examples.
To try the examples in your shell, copy your API key into your clipboard and
run:

```bash
export API_KEY=PASTE_API_KEY_HERE
```

Then you should be able to copy/paste any example from the docs. After pasting
a cURL example, you can pipe it to a JSON pretty printer to make it more
readable. Try [jsonpp](https://jmhodges.github.io/jsonpp/) or `json_pp` on OSX:

```bash
curl -s -H "X-IndeedAssessmentsToken: $API_KEY" \
  https://api.indeed-assessments.com/v1/bundles.json | json_pp
```


## JSON only

We use JSON for all API data. The style is no root element and snake\_case for
object keys. This means that you have to send the `Content-Type` header
`Content-Type: application/json; charset=utf-8` when you're **POSTing** or
**PUTing** data into Indeed Assessments. Appending `.json` to an endpoint path
is optional.


## Pagination

Most collection APIs paginate their results in order to keep response times
fast. If the request result is paginated, it will include a `meta` section with
the following information:

- **total_count**: The total elements in the collection.
- **count**: The total elements returned in the current request.
- **pages**: The number of pages for the result.

You can paginate the results by sending the following parameters in as part of
the query string of the request:

- **page**: The page that you want to retrieve.
- **per**: Total elements that you want per page.

For example, if you want the first page of bundles, with one element per page,
you'd do:

```bash
curl -s -H "X-IndeedAssessmentsToken: $API_KEY" \
  https://api.indeed-assessments.com/v1/bundles.json?page=1&per=1 | json_pp
```

And you would get:

```json
{
  "meta": {
    "total_count": 1,
    "count": 1,
    "pages": 1
  },
  "results": [
    {
      "bundle": {
        "id": "pgrnovpmee0qkljd",
        "name": "Frontend Engineer (JS Experience)",
        "description": "Lorem ipsum dolor sit amet",
        "completion_redirect_url": null,
        "status": "published_and_locked",
        "created_at": "2017-09-29T21:07:36.407Z",
        "updated_at": "2017-09-29T21:07:36.502Z",
        "url": "https://my-account.indeed-assessments.com/bundles/pgrnovpmee0qkljd",
        "assessments": [
          {
            "assessment": {
              "id": "are-you-a-human",
              "name": "Are You a Human",
              "description": "Basic test to ensure candidate is a human and not a robot or dog.",
              "automatically_scored": true,
              "estimated_duration": "0-15 minutes",
              "language": "English",
              "subject_category": "Aptitude \u0026 Psychometric",
              "preview_token": "X_FR3iXMbm8",
              "status": "published_and_locked",
              "created_at": "2017-09-29T21:07:35.390Z",
              "updated_at": "2017-09-29T21:07:35.856Z"
            }
          }
        ]
      }
    }
  ]
}
```


## Using HTTP caching

You must use HTTP freshness headers to speed up your application and lighten
the load on our servers. Most API responses will include an `ETag` or
`Last-Modified` header. When you first request a resource, store these values.
On subsequent requests, submit them back to us as `If-None-Match` and
`If-Modified-Since`, respectively. If the resource hasn't changed since your
last request, you'll get a 304 Not Modified response with no body, saving you
the time and bandwidth of sending something you already have.



## Handling errors

If we're having trouble, you might get a 5xx error. `500` means that the
application can't process the request for some reason, but `502 Bad Gateway`,
`503 Service Unavailable`, or `504 Gateway Timeout` errors are also possible.
In all of these cases, it's your responsibility to retry your request later.

You can also get error responses when creating resources via the API. In this
case, we'll try to show you a meaningful error. For example, if you try to
create a bundle without a `name`, you'll get a similar response to:

```json
{
  "error": "Validation failed: Name can't be blank"
}
```

In general, you should consider any non-200 HTTP response code an error.

## Rate limiting

You can perform up to 1 request per second per api key. If you exceed this
limit, you'll get a [429 Too Many
Requests](http://tools.ietf.org/html/draft-nottingham-http-new-status-02#section-4)
response for subsequent requests. Check the `Retry-After` header to learn how
many seconds to wait before retrying the request.

We recommend baking 429 response-handling in to your HTTP handling at a low
level so your integration handles retries gracefully and automatically.


## API endpoints

- [Assessments](sections/assessments.md#assessments)
- [Assignments](sections/assignments.md#assignments)
- [Attempts](sections/attempts.md#attempts)
- [Bundles](sections/bundles.md#bundles)


## Conduct

Please note that this project is released with a [Contributor Code of
Conduct](CONDUCT.md). By participating in discussions about the Indeed
Assessments API, you agree to abide by these terms.


---

If you have a specific feature request or find a bug, [please open a GitHub
issue](https://github.com/juandazapata/ia-api-docs/issues/new). We encourage
you to fork these docs for local reference and happily accept pull requests
with improvements.

To talk with us and other developers about the API, [post a question on
StackOverflow](http://stackoverflow.com/questions/ask) tagged
`indeed-assessments`. If you need help from us directly, please [open a support
ticket](https://indeed-assessments.com/support).
