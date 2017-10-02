# Indeed Assessments API

Welcome to the Indeed Assessments API. If you're looking to integrate your application with Indeed Assessments or create your own application in concert with data inside of Indeed Assessments, you're in the right place. We're happy to have you!


## Compatibility with previous APIs

The Indeed Assessments API is not compatible with the [Interviewed
API](https://github.com/prehire/interviewed-api). All integrations will start fresh with the new API. The core ingredients are the same, though: Indeed Assessments is a REST-style API that uses JSON for serialization.


## Making a request

All URLs start with **`https://api.indeed-assessments.com/v1/`**. URLs are HTTPS only. The latest version of the API is `v1`.

To make a request for all the projects on your account, append the `projects`
index path to the base URL to form something like
`https://3.basecampapi.com/999999999/projects.json`. In cURL, it looks like
this:

``` shell
curl -H "X-IndeedAssessmentsToken: $API_KEY" \
  https://3.basecampapi.com/999999999/projects.json
```

To create something, you also have to include the `Content-Type` header and the JSON data:

``` shell
curl -H "X-IndeedAssessmentsToken: $API_KEY" \
  -H 'Content-Type: application/json' \
  -d '{ "name": "My new project!" }' \
  https://3.basecampapi.com/999999999/projects.json
```

Throughout the Indeed Assessments API docs, we include "Copy as cURL" examples. To try the examples in your shell, copy your API key into your clipboard and run:

``` shell
export API_KEY=PASTE_API_KEY_HERE
```

Then you should be able to copy/paste any example from the docs. After pasting a cURL example, you can pipe it to a JSON pretty printer to make it more
readable. Try [jsonpp](https://jmhodges.github.io/jsonpp/) or `json_pp` on OSX:

``` shell
curl -s -H "X-IndeedAssessmentsToken: $API_KEY" \
  https://3.basecampapi.com/999999999/projects.json | json_pp
```


## JSON only

We use JSON for all API data. The style is no root element and snake\_case for object keys. This means that you have to send the `Content-Type` header
`Content-Type: application/json; charset=utf-8` when you're **POSTing** or **PUTing** data into Indeed Assessments. Appending `.json` to an endpoint path is optional.


## Pagination

Most collection APIs paginate their results. The number of requests that'll
appear on each page is variable. In most cases, we use a [geared pagination
ratio](https://github.com/basecamp/geared_pagination) with 15 results on page
1, 30 on page 2, 50 on 3, and then 100 on 4 and above. The Indeed Assessments
API follows the [RFC5988 convention](https://tools.ietf.org/html/rfc5988) of
using the `Link` header to provide URLs for the `next` page. Follow this
convention to retrieve the next page of data—please don't build the pagination
URLs yourself!

Here's an example response header from requesting the third page of
[messages](sections/messages.md#messages):

```
Link: <https://3.basecampapi.com/999999999/buckets/2085958496/messages.json?page=4>; rel="next"
```

If the `Link` header is blank, that's the last page. The Indeed Assessments API
also provides the `X-Total-Count` header, which displays the total number of resources in the collection you are fetching.


## Handling errors

If we're having trouble, you might get a 5xx error. `500` means that the application can't process the request for some reason, but `502 Bad Gateway`, `503 Service Unavailable`, or `504 Gateway Timeout` errors are also possible. In all of these cases, it's your responsibility to retry your request later.


## Rate limiting

You can perform up to 1 request per second from the same IP address for the same account. If you exceed this limit, you'll get a [429 Too Many Requests](http://tools.ietf.org/html/draft-nottingham-http-new-status-02#section-4) response for subsequent requests. Check the `Retry-After` header to learn how many seconds to wait before retrying the request.

We recommend baking 429 response-handling in to your HTTP handling at a low level so your integration handles retries gracefully and automatically.


## API endpoints

- [Attachments](https://github.com/basecamp/bc3-api/blob/master/sections/attachments.md#attachments)
- [Campfires](https://github.com/basecamp/bc3-api/blob/master/sections/campfires.md#campfires)
- [Chatbots](https://github.com/basecamp/bc3-api/blob/master/sections/chatbots.md#chatbots)
- [Client approvals](https://github.com/basecamp/bc3-api/blob/master/sections/client_approvals.md#client-approvals)
- [Client correspondences](https://github.com/basecamp/bc3-api/blob/master/sections/client_correspondences.md#client-correspondences)
- [Client replies](https://github.com/basecamp/bc3-api/blob/master/sections/client_replies.md#client-replies)
- [Comments](https://github.com/basecamp/bc3-api/blob/master/sections/comments.md#comments)
- [Documents](https://github.com/basecamp/bc3-api/blob/master/sections/documents.md#documents)
- [Events](https://github.com/basecamp/bc3-api/blob/master/sections/events.md#events)
- [Forwards](https://github.com/basecamp/bc3-api/blob/master/sections/forwards.md#forwards)
- [Inboxes](https://github.com/basecamp/bc3-api/blob/master/sections/inboxes.md#inboxes)
- [Message Boards](https://github.com/basecamp/bc3-api/blob/master/sections/message_boards.md#message-boards)
- [Messages](https://github.com/basecamp/bc3-api/blob/master/sections/messages.md#messages)
- [Message Types](https://github.com/basecamp/bc3-api/blob/master/sections/message_types.md#get-message-types)
- [People](https://github.com/basecamp/bc3-api/blob/master/sections/people.md#people)
- [Projects](https://github.com/basecamp/bc3-api/blob/master/sections/projects.md#projects)
- [Question answers](https://github.com/basecamp/bc3-api/blob/master/sections/question_answers.md#question-answers)
- [Questionnaires](https://github.com/basecamp/bc3-api/blob/master/sections/questionnaires.md#questionnaires)
- [Questions](https://github.com/basecamp/bc3-api/blob/master/sections/questions.md#questions)
- [Recordings](https://github.com/basecamp/bc3-api/blob/master/sections/recordings.md#recordings)
- [Schedule entries](https://github.com/basecamp/bc3-api/blob/master/sections/schedule_entries.md#schedule-entries)
- [Schedules](https://github.com/basecamp/bc3-api/blob/master/sections/schedules.md#schedules)
- [Templates](https://github.com/basecamp/bc3-api/blob/master/sections/templates.md#templates)
- [To-do lists](https://github.com/basecamp/bc3-api/blob/master/sections/todolists.md#to-do-lists)
- [To-dos](https://github.com/basecamp/bc3-api/blob/master/sections/todos.md#to-dos)
- [To-do sets](https://github.com/basecamp/bc3-api/blob/master/sections/todosets.md#to-do-sets)
- [Uploads](https://github.com/basecamp/bc3-api/blob/master/sections/uploads.md#uploads)
- [Vaults](https://github.com/basecamp/bc3-api/blob/master/sections/vaults.md#vaults)
- [Webhooks](https://github.com/basecamp/bc3-api/blob/master/sections/webhooks.md#webhooks)


## Conduct

Please note that this project is released with a [Contributor Code of
Conduct](CONDUCT.md). By participating in discussions about the Indeed Assessments API, you agree to abide by these terms.


---

If you have a specific feature request or find a bug, [please open a GitHub issue](https://github.com/juandazapata/ia-api-docs/issues/new). We encourage you to fork these docs for local reference and happily accept pull requests with
improvements.

To talk with us and other developers about the API, [post a question on StackOverflow](http://stackoverflow.com/questions/ask) tagged `indeed-assessments`. If you need help from us directly, please [open a support
ticket](https://indeed-assessments.com/support).