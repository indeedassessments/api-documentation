# Bundles

Endpoints:

- [Get all bundles](#get-all-bundles)
- [Get a bundle](#get-a-bundle)
- [Create a bundle](#create-a-bundle)
- [Update a bundle](#update-a-bundle)
- [Destroy a bundle](#destroy-a-bundle)


## Get all bundles

`GET /bundles.json` will return a [paginated list][pagination] of active
bundles, sorted by bundle name in alphabetical order. The results
include bundles that were created by your organization and those that are
part of the public library (bundles created by our team).

Each bundle includes the details for the assessments that are part of that
bundle.

###### Example JSON Response

```json
{
  "meta": {
    "total_count": 2,
    "count": 2,
    "pages": 1
  },
  "results": [
    {
      "bundle": {
        "id": "pgrnovpmee0qkljd",
        "name": "Frontend Engineer (JS Experience)",
        "description": "Test for assessing JS skills",
        "completion_redirect_url": null,
        "status": "published_and_locked",
        "created_at": "2017-09-29T21:07:36.407Z",
        "updated_at": "2017-09-29T21:07:36.502Z",
        "url": "https://yourcompany.indeed-assessments.com/bundles/pgrnovpmee0qkljd",
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
              "public_library": true,
              "status": "published_and_locked",
              "created_at": "2017-09-29T21:07:35.390Z",
              "updated_at": "2017-09-29T21:07:35.856Z"
            }
          }
        ]
      }
    },
    {
      "bundle": {
        "id": "4qaqmgyz6_bxf-cl",
        "name": "Poop bundle",
        "description": null,
        "completion_redirect_url": null,
        "status": "published_and_locked",
        "created_at": "2017-10-02T14:09:01.401Z",
        "updated_at": "2017-10-02T14:09:01.401Z",
        "url": "https://yourcompany.indeed-assessments.com/bundles/4qaqmgyz6_bxf-cl",
        "assessments": []
      }
    }
  ]
}

```

###### Copy as cURL

```bash
curl -s -H "X-IndeedAssessmentsToken: $API_KEY" \
  https://api.indeed-assessments.com/v1/bundles.json
```


## Get a bundle

* `GET /bundles/pgrnovpmee0qkljd.json` will return the bundle with the
  given `ID`, granted you have access to it.

###### Example JSON Response

```json
{
  "bundle": {
    "id": "pgrnovpmee0qkljd",
    "name": "Frontend Engineer (JS Experience)",
    "description": "Test for assessing JS skills",
    "completion_redirect_url": null,
    "status": "published_and_locked",
    "created_at": "2017-09-29T21:07:36.407Z",
    "updated_at": "2017-09-29T21:07:36.502Z",
    "url": "https://yourcompany.indeed-assessments.com/bundles/pgrnovpmee0qkljd",
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
          "public_library": true,
          "status": "published_and_locked",
          "created_at": "2017-09-29T21:07:35.390Z",
          "updated_at": "2017-09-29T21:07:35.856Z"
        }
      }
    ]
  }
}
```
###### Copy as cURL

```bash
curl -s -H "X-IndeedAssessmentsToken: $API_KEY" \
  https://api.indeed-assessments.com/v1/bundles/pgrnovpmee0qkljd.json
```


## Create a bundle

* `POST /bundles.json` creates a bundle for your organization.

**Parameters**:

- `name` _(mandatory)_ - The name of the bundle
- `description` _(optional)_ - A description of the bundle
- `completion_redirect_url` _(optional)_ - Redirect the user to a given URL after
  the user completes all the assessments in the bundle.
- `status` _(optional)_ - Defaults to `unpublished_and_unlocked` so you can add
  assessments to the bundle. Possible values are `unpublished_and_unlocked`,
  `published_and_locked` and `archived_and_locked`.

This endpoint will return `201 Created` with the JSON representation of the
bundle if the creation was a success. See the [Get a bundle](#get-a-bundle)
endpoint for more info on the payload.


###### Example JSON Request

``` json
{
  "name": "My new bundle"
}
```

###### Copy as cURL

```bash
curl -s -H "X-IndeedAssessmentsToken: $API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"name":"My new bundle"}' \
  https://api.indeed-assessments.com/v1/bundles.json
```


## Update a bundle

* `PUT /bundles/pgrnovpmee0qkljd.json` allows changing attributes of a bundle
  and change its publication status.

This endpoint will return `200 OK` with the JSON representation of the bundle
if the update was a success. See the [Get a bundle](#get-a-bundle)
endpoint for more info on the payload.


###### Example JSON Request

``` json
{
  "name": "My new name for the bundle"
}
```

###### Copy as cURL

```bash
curl -s -H "X-IndeedAssessmentsToken: $API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"name":"My new name for the bundle bundle"}' \
  -X PUT \
  https://api.indeed-assessments.com/v1/bundles/pgrnovpmee0qkljd.json
```


## Destroy a bundle

* `DELETE /bundles/pgrnovpmee0qkljd.json` will delete the given bundle if the
  bundle wasn't previously published.

No params required. This endpoint will return `204 No Content` if successful.

You can only delete bundles if they are in the `unpublished_and_unlocked`
status, otherwise, the deletion is not permitted.

If you want to "unpublish" a bundle, please see the [Update a
bundle](#update-a-bundle) and pass the new `status` with a value of
`archived_and_locked`.

###### Copy as cURL

```bash
curl -s -H "X-IndeedAssessmentsToken: $API_KEY" \
  -H "Content-Type: application/json" \
  -X DELETE \
  https://api.indeed-assessments.com/v1/bundles/pgrnovpmee0qkljd.json
```

[pagination]: https://github.com/juandazapata/ia-api-docs/blob/master/README.md#pagination
