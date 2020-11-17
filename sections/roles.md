# Roles

Endpoints:

- [Get all roles](#get-all-roles)
- [Get a role](#get-a-role)
- [Create a role](#create-a-role)
- [Add an assessment to a role](#add-an-assessment-to-a-role)
- [Remove an assessment from a role](#remove-an-assessment-from-a-role)
- [Update a role](#update-a-role)
- [Destroy a role](#destroy-a-role)


## Get all roles

`GET /roles.json` will return a [paginated list][pagination] of active
roles, sorted by role name in alphabetical order. The results
include roles that were created by your organization and those that are
part of the public library (roles created by our team).

Each role includes the details for the assessments that are part of that
role.

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
      "role": {
        "id": "pgrnovpmee0qkljd",
        "name": "Frontend Engineer (JS Experience)",
        "description": "Test for assessing JS skills",
        "completion_redirect_url": null,
        "status": "published_and_locked",
        "created_at": "2017-09-29T21:07:36.407Z",
        "updated_at": "2017-09-29T21:07:36.502Z",
        "url": "https://yourcompany.indeedassessments.com/roles/pgrnovpmee0qkljd",
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
      "role": {
        "id": "4qaqmgyz6_bxf-cl",
        "name": "Backend Engineer (Ruby on Rails)",
        "description": null,
        "completion_redirect_url": null,
        "status": "published_and_locked",
        "created_at": "2017-10-02T14:09:01.401Z",
        "updated_at": "2017-10-02T14:09:01.401Z",
        "url": "https://yourcompany.indeedassessments.com/roles/4qaqmgyz6_bxf-cl",
        "assessments": []
      }
    }
  ]
}

```

###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  https://api.indeedassessments.com/v1/roles.json
```


## Get a role

* `GET /roles/pgrnovpmee0qkljd.json` will return the role with the
  given `ID`, granted you have access to it.

###### Example JSON Response

```json
{
  "role": {
    "id": "pgrnovpmee0qkljd",
    "name": "Frontend Engineer (JS Experience)",
    "description": "Test for assessing JS skills",
    "completion_redirect_url": null,
    "status": "published_and_locked",
    "created_at": "2017-09-29T21:07:36.407Z",
    "updated_at": "2017-09-29T21:07:36.502Z",
    "url": "https://yourcompany.indeedassessments.com/roles/pgrnovpmee0qkljd",
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
curl -s -H "Authorization: token $API_KEY" \
  https://api.indeedassessments.com/v1/roles/pgrnovpmee0qkljd.json
```


## Create a role

* `POST /roles.json` creates a role for your organization.

**Parameters**:

- `name` _(mandatory)_ - The name of the role
- `status` _(mandatory)_ - Possible values are `unpublished_and_unlocked`,
  `published_and_locked` and `archived_and_locked`. When creating a new role,
  you must pass `unpublished_and_unlocked` so you can add assessments to the
  role.
- `description` _(optional)_ - A description of the role
- `completion_redirect_url` _(optional)_ - Redirect the user to a given URL after
  the user completes all the assessments in the role.

This endpoint will return `201 Created` with the JSON representation of the
role if the creation was a success. See the [Get a role](#get-a-role)
endpoint for more info on the payload.


###### Example JSON Request

``` json
{
  "name": "My new role",
  "status": "unpublished_and_unlocked"
}
```

###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"name":"My new role", "status":"unpublished_and_unlocked"}' \
  https://api.indeedassessments.com/v1/roles.json
```


## Add an Assessment to a Role

* `POST /roles/pgrnovpmee0qkljd/assessments.json` adds one or more assessments
  to a given role in your organization.

**Parameters**:

- `assessment_id` _(mandatory)_ - The ID of the assessments that you want to
  add to the role.

This endpoint will return `201 Created` with the JSON representation of the
role if the creation was a success. See the [Get a role](#get-a-role)
endpoint for more info on the payload.

**Please note that you can add assessments to a role, only if the role status
is `unpublished_and_unlocked` and the assessment status is
`published_and_locked`**


###### Example JSON Request

``` json
{
  "assessment_id": "are-you-a-human"
}
```

###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  -H "Content-Type: application/json" \
  -d '{assessment_id: "are-you-a-human"}' \
  https://api.indeedassessments.com/v1/roles/pgrnovpmee0qkljd/assessments.json
```


## Remove an Assessment from a Role

* `DELETE /roles/pgrnovpmee0qkljd/assessments/are-you-human.json` removes the
  `are-you-human` assessment from the `pgrnovpmee0qkljd` role.

This endpoint will return `204 No Content` if successful.

**Please note that you can remove assessments from a role, only if the role status
is `unpublished_and_unlocked`**


###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  -H "Content-Type: application/json" \
  -X DELETE \
  https://api.indeedassessments.com/v1/roles/pgrnovpmee0qkljd/assessments/are-you-human.json
```


## Update a Role

* `PUT /roles/pgrnovpmee0qkljd.json` allows changing attributes of a role
  and change its publication status.

This endpoint will return `200 OK` with the JSON representation of the role
if the update was a success. See the [Get a role](#get-a-role)
endpoint for more info on the payload.


###### Example JSON Request

``` json
{
  "name": "My new name for the role"
}
```

###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"name":"My new name for the role"}' \
  -X PUT \
  https://api.indeedassessments.com/v1/roles/pgrnovpmee0qkljd.json
```


## Archive a Role

* `DELETE /roles/pgrnovpmee0qkljd.json` will archive the given role even if the
  role wasn't previously published.

This endpoint will return `204 No Content` if successful.

###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  -H "Content-Type: application/json" \
  -X DELETE \
  https://api.indeedassessments.com/v1/roles/pgrnovpmee0qkljd.json
```

[pagination]: https://github.com/juandazapata/ia-api-docs/blob/master/README.md#pagination
