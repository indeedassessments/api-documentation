# Assignments

Endpoints:

- [Get all assignments](#get-all-assignments)
- [Get an assignment](#get-an-assignment)
- [Create an assignment](#create-an-assignment)


## Get all assignments

`GET /assignments.json` will return a [paginated list][pagination] of
assignments, sorted by creation date in descending order (newest assignments
are displayed first).

###### Example JSON Response

```json
{
  "meta": {
    "total_count": 1,
    "count": 1,
    "pages": 1
  },
  "results": [
    {
      "assignment": {
        "id": "832uwyzirea9ftehxuwya38",
        "remaining_asssessment_count": 0,
        "score": 100,
        "possible_score": 100,
        "weighted_percentage_score": 100,
        "pending_review_count": 1,
        "completion_redirect_url": null,
        "progress": "complete",
        "created_at": "2017-09-29T21:07:36.407Z",
        "updated_at": "2017-09-29T21:07:36.502Z",
        "url": "https://yourcompany.indeed-assessments.com/assignments/832uwyzirea9ftehxuwya38",
        "bundle": {
          "id": "pgrnovpmee0qkljd",
          "name": "Frontend Engineer (JS Experience)",
          "attempt_ids": [133, 182, 293]
        },
        "user": {
          "email": "john.doe@example.com",
          "full_name": "John Doe"
        }
      }
    }
  ]
}

```

###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  https://api.indeed-assessments.com/v1/assignments.json
```


## Get an assignment

* `GET /assignments/832uwyzirea9ftehxuwya38.json` will return the assignment
  with the given `ID`, granted you have access to it.

###### Example JSON Response

```json
{
  "assignment": {
    "id": "832uwyzirea9ftehxuwya38",
    "remaining_asssessment_count": 0,
    "score": 100,
    "possible_score": 100,
    "weighted_percentage_score": 100,
    "pending_review_count": 1,
    "completion_redirect_url": null,
    "progress": "complete",
    "created_at": "2017-09-29T21:07:36.407Z",
    "updated_at": "2017-09-29T21:07:36.502Z",
    "url": "https://yourcompany.indeed-assessments.com/assignments/832uwyzirea9ftehxuwya38",
    "bundle": {
      "id": "pgrnovpmee0qkljd",
      "name": "Frontend Engineer (JS Experience)",
      "attempt_ids": [133, 182, 293]
    },
    "user": {
      "email": "john.doe@example.com",
      "full_name": "John Doe"
    }
  }
}
```

###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  https://api.indeed-assessments.com/v1/assignments/832uwyzirea9ftehxuwya38.json
```


## Create an assignment

* `POST /assignments.json` creates an assignment for your organization.

**Parameters**:

- `email` _(mandatory)_ - The email of the user that you want to take the
  assessments in the bundle.
- `bundle_id` _(mandatory if `assessment_ids` is not present)_ - The bundle
  that you want the user to take
- `assessments_id` _(mandatory if `bundle_id` is not present)_ - An array of
  assessment ids that you want the user to take additionally to the assessments
  that are in the bundle.

You must provide either `bundle_id` or `assessments_id` in your request.

This endpoint will return `201 Created` with the JSON representation of the
assignment if the creation was a success. See the [Get an
assignment](#get-an-assignment)
endpoint for more info on the payload.

Please note that a successful creation will send an email message to the
user, with an invitation to take the assessments.


###### Example JSON Request

``` json
{
  "bundle_id": "pgrnovpmee0qkljd",
  "email": "john.doe@example.com"
}
```

###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"bundle_id":"pgrnovpmee0qkljd", "email":"john.doe@example.com"}' \
  https://api.indeed-assessments.com/v1/assignments.json
```

[pagination]: https://github.com/juandazapata/ia-api-docs/blob/master/README.md#pagination
