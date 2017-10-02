# Attempts

Endpoints:

- [Get an attempt](#get-an-attempt)


## Get an attempt

* `GET /attempts/123.json` will return the attempt with the given `ID`, granted
  you have access to it.

###### Example JSON Response

```json
{
  "attempt": {
    "id": 123,
    "completion_time_in_seconds": 239,
    "score": 19,
    "possible_score": 100,
    "percentage_score": 19,
    "scoring_completed": true,
    "pending_review_count": 0,
    "preview": false,
    "started_at": "2017-09-29T21:07:36.407Z",
    "completed_at": "2017-09-29T21:07:36.407Z",
    "created_at": "2017-09-29T21:07:36.407Z",
    "updated_at": "2017-09-29T21:07:36.502Z",
    "bundle": {
      "id": "pgrnovpmee0qkljd",
      "name": "Frontend Engineer (JS Experience)"
    },
    "assessment": {
      "id": "are-you-a-human",
      "name": "Are You a Human",
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
  https://api.indeed-assessments.com/v1/attempts/123.json
```

[pagination]: https://github.com/juandazapata/ia-api-docs/blob/master/README.md#pagination
