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
            "transcription_1_raw": "She's one of those low-talkers. You can't hear a word she's saying!",
            "transcription_1_status": "The sea was angry that day my friends.",
            "transcription_1_confidence": "0.0",
            "transcription_2": "But I don't want to be a pirate!",
            "transcription_2_raw": "She had man hands.",
            "transcription_2_status": "It's Fusilli Jerry!",
            "transcription_2_confidence": "3.0",
            "transcription_3": "This isn't a good time",
            "transcription_3_raw": "You're becoming one of the glitterati",
            "transcription_3_status": "Hello, Newman.",
            "transcription_3_confidence": "2.0",
            "audio_prompt": {
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
            "debug_ip": "0.0.0.0",
            "debug_user_agent": "agent",
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
}

```

###### Copy as cURL

```bash
curl -s -H "Authorization: token $API_KEY" \
  https://api.indeedassessments.com/v1/attempts/123.json
```

[pagination]: https://github.com/juandazapata/ia-api-docs/blob/master/README.md#pagination
