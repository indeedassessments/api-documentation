# Assignments

Endpoints:

- [Get all assignments](#get-all-assignments)
- [Get an assignment](#get-an-assignment)
- [Create an assignment](#create-an-assignment)


## Get all assignments

`GET /assignments.json` will return a [paginated list][pagination] of
assignments, sorted by creation date in descending order (newest assignments
are displayed first).

_Note:_ Questions and their details, including candidate answers, will **not** appear in the response for assignment attempts of public assessments.


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
        "id": "yw4gmpjjtkgkdxjkuoghsa",
        "remaining_assessment_count": 0,
        "completion_redirect_url": null,
        "external_job_id": null,
        "external_candidacy_id": null,
        "external_person_id": null,
        "created_at": "2017-12-08T13:38:16.556Z",
        "updated_at": "2017-12-08T13:38:17.560Z",
        "score": 2.0,
        "possible_score": 2.0,
        "weighted_percentage_score": 1.0,
        "invitation_url": "http://lang-group-33uekq.i9d.me:9887/c/start_next/xkxtl4xt_ft2cyfckui2yg/bzXUhnAktXE9pD_iQy7y",
        "public_results_url": "http://lang-group-33uekq.i9d.me:9887/share_assignment/yw4gmpjjtkgkdxjkuoghsa",
        "role": {
          "id": "gih3cv7f6a9ixgjt",
          "name": "Milky Way 1"
        },
        "user": {
          "id": "anonymous-candidate",
          "name": "Anonymous Candidate 514",
          "email": "some-user0@example.com"
        },
        "attempts": [
          {
            "id": "khbgltqixvvyoxeb",
            "completion_time_in_seconds": 1512740297,
            "scoring_completed": true,
            "pending_review_count": 0,
            "started_at": "2017-12-08T13:38:17.434Z",
            "completed_at": "2017-12-08T13:38:17.434Z",
            "created_at": "2017-12-08T13:38:16.627Z",
            "updated_at": "2017-12-08T13:38:17.550Z",
            "score": 2.0,
            "possible_score": 2.0,
            "percentage_score": 1.0,
            "assessment": {
              "id": "pjpmahbioyqufxos",
              "name": "Philosopher Assessment 1"
            },
            "step_progressions": [
              {
                "answers": [
                  {
                    "value": null,
                    "question": {
                      "id": "zhw2jhjqydhdrzlz",
                      "label": "If they follow standard Imperial procedure, theyll dump their garbage before they go to light-speed.",
                      "instructions": "Help instructions for a question type of type Single line text with a question scoring rule",
                      "choices": [

                      ]
                    },
                    "select_choices": [

                    ],
                    "scores": [

                    ]
                  },
                  {
                    "value": "This Lime Tree Bower",
                    "question": {
                      "id": "zhw2jhjqydhdrzlz",
                      "label": "If they follow standard Imperial procedure, theyll dump their garbage before they go to light-speed.",
                      "instructions": "Help instructions for a question type of type Single line text with a question scoring rule",
                      "choices": [

                      ]
                    },
                    "select_choices": [

                    ],
                    "scores": [
                      {
                        "score": 1.0,
                        "possible_score": 1.0,
                        "scoring_dimension_name": "Sales > Math"
                      }
                    ]
                  },
                  {
                    "value": null,
                    "question": {
                      "id": "u8ufjuh5dh5qdri",
                      "label": "If they follow standard Imperial procedure, theyll dump their garbage before they go to light-speed.",
                      "instructions": "Help instructions for a question type of type Paragraph text with a question scoring rule",
                      "choices": [

                      ]
                    },
                    "select_choices": [

                    ],
                    "scores": [

                    ]
                  },
                  {
                    "value": "A Passage to India",
                    "question": {
                      "id": "u8ufjuh5dh5qdri",
                      "label": "If they follow standard Imperial procedure, theyll dump their garbage before they go to light-speed.",
                      "instructions": "Help instructions for a question type of type Paragraph text with a question scoring rule",
                      "choices": [

                      ]
                    },
                    "select_choices": [

                    ],
                    "scores": [
                      {
                        "score": 1.0,
                        "possible_score": 1.0,
                        "scoring_dimension_name": "Friendliness"
                      }
                    ]
                  },
                  {
                    "value": null,
                    "question": {
                      "id": "zhjhofglmrzw4o40",
                      "label": "If they follow standard Imperial procedure, theyll dump their garbage before they go to light-speed.",
                      "instructions": "Help instructions for a question type of type Static text",
                      "choices": [
                        {
                          "id": "gc5ixhi9ci9d-miw",
                          "value": "If you want to know what a mans like, take a good look at how he treats his inferiors, not his equals. (1)",
                          "correct_answer": false
                        },
                        {
                          "id": "fctk69mxdnv_pw8d",
                          "value": "To the well-organized mind, death is but the next great adventure. (2)",
                          "correct_answer": false
                        },
                        {
                          "id": "aesr6xnq_3_he2_g",
                          "value": "Never trust anything that can think for itself if you cant see where it keeps its brain. (3)",
                          "correct_answer": false
                        },
                        {
                          "id": "fdj_3tzvpp8cwsaz",
                          "value": "Things we lose have a way of coming back to us in the end, if not always in the way we expect. (4)",
                          "correct_answer": false
                        },
                        {
                          "id": "jzmmr4qf85el_zrs",
                          "value": "It is our choices, Harry, that show what we truly are, far more than our abilities. (5)",
                          "correct_answer": false
                        }
                      ]
                    },
                    "select_choices": [

                    ],
                    "scores": [

                    ]
                  },
                  {
                    "value": "If you want to know what a mans like, take a good look at how he treats his inferiors, not his equals. (1), To the well-organized mind, death is but the next great adventure. (2)",
                    "question": {
                      "id": "zhjhofglmrzw4o40",
                      "label": "If they follow standard Imperial procedure, theyll dump their garbage before they go to light-speed.",
                      "instructions": "Help instructions for a question type of type Static text",
                      "choices": [
                        {
                          "id": "gc5ixhi9ci9d-miw",
                          "value": "If you want to know what a mans like, take a good look at how he treats his inferiors, not his equals. (1)",
                          "correct_answer": false
                        },
                        {
                          "id": "fctk69mxdnv_pw8d",
                          "value": "To the well-organized mind, death is but the next great adventure. (2)",
                          "correct_answer": false
                        },
                        {
                          "id": "aesr6xnq_3_he2_g",
                          "value": "Never trust anything that can think for itself if you cant see where it keeps its brain. (3)",
                          "correct_answer": false
                        },
                        {
                          "id": "fdj_3tzvpp8cwsaz",
                          "value": "Things we lose have a way of coming back to us in the end, if not always in the way we expect. (4)",
                          "correct_answer": false
                        },
                        {
                          "id": "jzmmr4qf85el_zrs",
                          "value": "It is our choices, Harry, that show what we truly are, far more than our abilities. (5)",
                          "correct_answer": false
                        }
                      ]
                    },
                    "select_choices": [
                      {
                        "id": "gc5ixhi9ci9d-miw",
                        "value": "If you want to know what a mans like, take a good look at how he treats his inferiors, not his equals. (1)",
                        "correct_answer": false
                      },
                      {
                        "id": "fctk69mxdnv_pw8d",
                        "value": "To the well-organized mind, death is but the next great adventure. (2)",
                        "correct_answer": false
                      }
                    ],
                    "scores": [

                    ]
                  }
                ],
                "step": {
                  "name": "A demo step",
                  "sequence": 1
                },
                "started_at": "2017-12-08T13:38:17.357Z",
                "completed_at": "2017-12-08T13:38:17.412Z",
                "timed_out": false,
                "completion_time_in_seconds": 0
              }
            ]
          }
        ]
      }
    }
  ]
}

```

###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  https://api.indeedassessments.com/v1/assignments.json
```


## Get an assignment

* `GET /assignments/832uwyzirea9ftehxuwya38.json` will return the assignment
  with the given `ID`, granted you have access to it.

_Note:_ Questions and their details, including candidate answers, will **not** appear in the response for assignment attempts of public assessments.

###### Example JSON Response

```json
{
  "assignment": {
    "id": "yw4gmpjjtkgkdxjkuoghsa",
    "remaining_assessment_count": 0,
    "completion_redirect_url": null,
    "external_job_id": null,
    "external_candidacy_id": null,
    "external_person_id": null,
    "created_at": "2017-12-08T13:38:16.556Z",
    "updated_at": "2017-12-08T13:38:17.560Z",
    "score": 2.0,
    "possible_score": 2.0,
    "weighted_percentage_score": 1.0,
    "invitation_url": "http://lang-group-33uekq.i9d.me:9887/c/start_next/xkxtl4xt_ft2cyfckui2yg/bzXUhnAktXE9pD_iQy7y",
    "public_results_url": "http://lang-group-33uekq.i9d.me:9887/share_assignment/yw4gmpjjtkgkdxjkuoghsa",
    "role": {
      "id": "gih3cv7f6a9ixgjt",
      "name": "Milky Way 1"
    },
    "user": {
      "id": "anonymous-candidate",
      "name": "Anonymous Candidate 514",
      "email": "some-user0@example.com"
    },
    "attempts": [
      {
        "id": "khbgltqixvvyoxeb",
        "completion_time_in_seconds": 1512740297,
        "scoring_completed": true,
        "pending_review_count": 0,
        "started_at": "2017-12-08T13:38:17.434Z",
        "completed_at": "2017-12-08T13:38:17.434Z",
        "created_at": "2017-12-08T13:38:16.627Z",
        "updated_at": "2017-12-08T13:38:17.550Z",
        "score": 2.0,
        "possible_score": 2.0,
        "percentage_score": 1.0,
        "level": "Proficient",
        "assessment": {
          "id": "pjpmahbioyqufxos",
          "name": "Philosopher Assessment 1"
        },
        "step_progressions": [
          {
            "answers": [
              {
                "value": null,
                "question": {
                  "id": "zhw2jhjqydhdrzlz",
                  "label": "If they follow standard Imperial procedure, theyll dump their garbage before they go to light-speed.",
                  "instructions": "Help instructions for a question type of type Single line text with a question scoring rule",
                  "choices": [

                  ]
                },
                "select_choices": [

                ],
                "scores": [

                ]
              },
              {
                "value": "This Lime Tree Bower",
                "question": {
                  "id": "zhw2jhjqydhdrzlz",
                  "label": "If they follow standard Imperial procedure, theyll dump their garbage before they go to light-speed.",
                  "instructions": "Help instructions for a question type of type Single line text with a question scoring rule",
                  "choices": [

                  ]
                },
                "select_choices": [

                ],
                "scores": [
                  {
                    "score": 1.0,
                    "possible_score": 1.0,
                    "scoring_dimension_name": "Sales > Math"
                  }
                ]
              },
              {
                "value": null,
                "question": {
                  "id": "u8ufjuh5dh5qdri",
                  "label": "If they follow standard Imperial procedure, theyll dump their garbage before they go to light-speed.",
                  "instructions": "Help instructions for a question type of type Paragraph text with a question scoring rule",
                  "choices": [

                  ]
                },
                "select_choices": [

                ],
                "scores": [

                ]
              },
              {
                "value": "A Passage to India",
                "question": {
                  "id": "u8ufjuh5dh5qdri",
                  "label": "If they follow standard Imperial procedure, theyll dump their garbage before they go to light-speed.",
                  "instructions": "Help instructions for a question type of type Paragraph text with a question scoring rule",
                  "choices": [

                  ]
                },
                "select_choices": [

                ],
                "scores": [
                  {
                    "score": 1.0,
                    "possible_score": 1.0,
                    "scoring_dimension_name": "Friendliness"
                  }
                ]
              },
              {
                "value": null,
                "question": {
                  "id": "zhjhofglmrzw4o40",
                  "label": "If they follow standard Imperial procedure, theyll dump their garbage before they go to light-speed.",
                  "instructions": "Help instructions for a question type of type Static text",
                  "choices": [
                    {
                      "id": "gc5ixhi9ci9d-miw",
                      "value": "If you want to know what a mans like, take a good look at how he treats his inferiors, not his equals. (1)",
                      "correct_answer": false
                    },
                    {
                      "id": "fctk69mxdnv_pw8d",
                      "value": "To the well-organized mind, death is but the next great adventure. (2)",
                      "correct_answer": false
                    },
                    {
                      "id": "aesr6xnq_3_he2_g",
                      "value": "Never trust anything that can think for itself if you cant see where it keeps its brain. (3)",
                      "correct_answer": false
                    },
                    {
                      "id": "fdj_3tzvpp8cwsaz",
                      "value": "Things we lose have a way of coming back to us in the end, if not always in the way we expect. (4)",
                      "correct_answer": false
                    },
                    {
                      "id": "jzmmr4qf85el_zrs",
                      "value": "It is our choices, Harry, that show what we truly are, far more than our abilities. (5)",
                      "correct_answer": false
                    }
                  ]
                },
                "select_choices": [

                ],
                "scores": [

                ]
              },
              {
                "value": "If you want to know what a mans like, take a good look at how he treats his inferiors, not his equals. (1), To the well-organized mind, death is but the next great adventure. (2)",
                "question": {
                  "id": "zhjhofglmrzw4o40",
                  "label": "If they follow standard Imperial procedure, theyll dump their garbage before they go to light-speed.",
                  "instructions": "Help instructions for a question type of type Static text",
                  "choices": [
                    {
                      "id": "gc5ixhi9ci9d-miw",
                      "value": "If you want to know what a mans like, take a good look at how he treats his inferiors, not his equals. (1)",
                      "correct_answer": false
                    },
                    {
                      "id": "fctk69mxdnv_pw8d",
                      "value": "To the well-organized mind, death is but the next great adventure. (2)",
                      "correct_answer": false
                    },
                    {
                      "id": "aesr6xnq_3_he2_g",
                      "value": "Never trust anything that can think for itself if you cant see where it keeps its brain. (3)",
                      "correct_answer": false
                    },
                    {
                      "id": "fdj_3tzvpp8cwsaz",
                      "value": "Things we lose have a way of coming back to us in the end, if not always in the way we expect. (4)",
                      "correct_answer": false
                    },
                    {
                      "id": "jzmmr4qf85el_zrs",
                      "value": "It is our choices, Harry, that show what we truly are, far more than our abilities. (5)",
                      "correct_answer": false
                    }
                  ]
                },
                "select_choices": [
                  {
                    "id": "gc5ixhi9ci9d-miw",
                    "value": "If you want to know what a mans like, take a good look at how he treats his inferiors, not his equals. (1)",
                    "correct_answer": false
                  },
                  {
                    "id": "fctk69mxdnv_pw8d",
                    "value": "To the well-organized mind, death is but the next great adventure. (2)",
                    "correct_answer": false
                  }
                ],
                "scores": [

                ]
              }
            ],
            "step": {
              "name": "A demo step",
              "sequence": 1
            },
            "started_at": "2017-12-08T13:38:17.357Z",
            "completed_at": "2017-12-08T13:38:17.412Z",
            "timed_out": false,
            "completion_time_in_seconds": 0
          },
          {
            "audio_recordings": [
              {
                "url": "http: //stromansatterfield.name/cayla",
                "size": 107,
                "duration": 69,
                "created_at": "2018-01-23T13: 50: 17.192Z",
                "updated_at": "2018-01-23T13: 50: 17.192Z",
                "transcription_1": "You're gonna over-dry your laundry?",
                "transcription_1_status": "The sea was angry that day my friends.",
                "transcription_1_confidence": "0.0",
                "transcription_2": "But I don't want to be a pirate!",
                "transcription_2_status": "It's Fusilli Jerry!",
                "transcription_2_confidence": "3.0",
                "transcription_3": "This isn't a good time",
                "transcription_3_status": "Hello, Newman.",
                "transcription_3_confidence": "2.0",
                "audio_prompt": {
                  "id": "rhfydjeihete_yhg",
                  "name": "This woman hates me so much, I'm starting to like her",
                  "url": "http: //nikolaus.biz/jasen",
                  "sequence": "1.0",
                  "record_after_prompt": true,
                  "text_to_speech": "Cartwright! Cartwright!",
                  "text_to_speech_url": "http: //skiles.biz/naomie_cartwright",
                  "text_to_speech_voice": "English - Julie (US Female)"
                }
              }
            ],
            "answers": [

            ],
            "step": {
              "name": "A audio interview step",
              "sequence": 1
            },
            "started_at": "2018-01-23T13: 50: 17.149Z",
            "completed_at": "2018-01-23T13: 50: 17.202Z",
            "timed_out": false,
            "completion_time_in_seconds": 0
          },
          {
            "video_recordings": [
              {
                "url": "http: //yundt.com/cory",
                "file_size": 249,
                "duration": 79,
                "created_at": "2018-01-23T16: 17: 27.999Z",
                "updated_at": "2018-01-23T16: 17: 27.999Z",
                "practice": false,
                "video_prompt": {
                  "name": "This woman hates me so much, I'm starting to like her",
                  "sequence": "1.0",
                  "text_prompt": "You're gonna over-dry your laundry?",
                  "retakes": 0,
                  "time_limit_in_seconds": 60
                }
              }
            ],
            "answers": [

            ],
            "step": {
              "name": "A video interview step",
              "sequence": 1
            },
            "started_at": "2018-01-23T16: 17: 27.964Z",
            "completed_at": "2018-01-23T16: 17: 28.008Z",
            "timed_out": false,
            "completion_time_in_seconds": 0
          }
        ]
      }
    ]
  }
}
```

###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  https://api.indeedassessments.com/v1/assignments/832uwyzirea9ftehxuwya38.json
```


## Create an assignment

* `POST /assignments.json` creates an assignment for your organization.

**Parameters**:

- `email` _(mandatory)_ - The email of the user that you want to take the
  assessments in the role.
- `role_id` _(mandatory)_ - The role
  that you want the user to take
- `completion_webhook_url` _(optional)_ - Creates a webhook in Indeed Assessments.
  The url will be called upon the completion of an assignment. If used, the value 
  must not be blank
- `completion_webhook_name` _(optional)_ - Defines the name of the webhook defined 
  by `completion_webhook_url`. It is not required if `completion_webhook_url` is
  used, but it is helpful to the admin to know what the webhook is for.

This endpoint will return `201 Created` with the JSON representation of the
assignment if the creation was a success. See the [Get an
assignment](#get-an-assignment)
endpoint for more info on the payload.

Please note that a successful creation will send an email message to the
user, with an invitation to take the assessments.


###### Example JSON Request

``` json
{
  "role_id": "pgrnovpmee0qkljd",
  "email": "john.doe@example.com"
}
```

###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"role_id":"pgrnovpmee0qkljd", "email":"john.doe@example.com"}' \
  https://api.indeedassessments.com/v1/assignments.json
```

###### Example JSON Request with completion_webhook_url

``` json
{
  "role_id": "pgrnovpmee0qkljd",
  "email": "john.doe@example.com",
  "completion_webhook_url": "http://some.url.net/things?and=stuff&more_things=more_stuff",
  "completion_webhook_name": "webhooks!"
}
```

[pagination]: https://github.com/juandazapata/ia-api-docs/blob/master/README.md#pagination
