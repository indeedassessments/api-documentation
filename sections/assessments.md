# Assessments

Endpoints:

- [Get all assessments](#get-all-assessments)
- [Get an assessment](#get-an-assessment)
- [Clone an assessment](#clone-an-assessment)


## Get all assessments

`GET /assessments.json` will return a [paginated list][pagination] of active
assessments, sorted by assessment name in alphabetical order. The results
include assessments that were created by your organization and those that are
part of the public library (assessments created by our team).

Custom assessments include information about the steps and questions that you
define in builder (only form questions are supported).

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
        "updated_at": "2017-09-29T21:07:36.125Z",
        "steps": {
          "step": {
            "type": "reform",
            "name": "A demo step",
            "time_limit_in_seconds": null,
            "instructions": "Answer the following correctly",
            "instructions_type": null,
            "questions": [
              {
                "type": "single_line_text",
                "label": "How would you use an abacus?"
              }
            ]
          }
        }
      }
    }
  ]
}
```

###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  https://api.indeedassessments.com/v1/assessments.json
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
curl -s -H "Authorization: token $API_KEY" \
  https://api.indeedassessments.com/v1/assessments/are-you-a-human.json
```

## Clone an assessment

* `POST /assessments/are-you-a-human/clone.json` will clone the assessment with the
  given `ID`, and return the newly created cloned assessment.

**Parameters**:

- `name` _(optional)_ - The name you want to use for the new assessment.

This endpoint will return `201 Created` with the JSON representation of the
assessment if the creation was a success.

###### Example JSON Response

```json
{
  "assessment": {
    "id": "are-you-a-human-2",
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
curl -s -H "Authorization: token $API_KEY" \
  https://api.indeedassessments.com/v1/assessments/are-you-a-human/clone.json
```

[pagination]: https://github.com/juandazapata/ia-api-docs/blob/master/README.md#pagination
