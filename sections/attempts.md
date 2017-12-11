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
}

```

###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  https://api.indeedassessments.com/v1/attempts/123.json
```

[pagination]: https://github.com/juandazapata/ia-api-docs/blob/master/README.md#pagination
