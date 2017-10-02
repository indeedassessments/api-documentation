# Assessments

Endpoints:

- [Get all assessments](#get-all-assessments)
- [Get an assessment](#get-an-assessment)


## Get all assessments

`GET /assessments.json` will return a [paginated list][pagination] of active
assessments, sorted by assessment name in alphabetical order. The results
include assessments that were created by your organization and those that are
part of the public library (assessments created by our team).

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
    },
    {
      "assessment": {
        "id": "can-you-math",
        "name": "Can You Math?",
        "description": "Some math",
        "automatically_scored": true,
        "estimated_duration": "0-15 minutes",
        "language": "English",
        "subject_category": "Aptitude \u0026 Psychometric",
        "preview_token": "X_FR3iXMbm8",
        "public_library": false,
        "status": "published_and_locked",
        "created_at": "2017-09-29T21:07:36.001Z",
        "updated_at": "2017-09-29T21:07:36.125Z"
      }
    }
  ]
}
```

###### Copy as cURL

```bash
curl -s -H "X-IndeedAssessmentsToken: $API_KEY" \
  https://api.indeed-assessments.com/v1/assessments.json
```


## Get an assessment

* `GET /assessments/are-you-a-human.json` will return the assessment with the
  given `ID`, granted you have access to it.

###### Example JSON Response

```json
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
```
###### Copy as cURL

```bash
curl -s -H "X-IndeedAssessmentsToken: $API_KEY" \
  https://api.indeed-assessments.com/v1/assessments/are-you-a-human.json
```


[pagination]: https://github.com/juandazapata/ia-api-docs/blob/master/README.md#pagination
