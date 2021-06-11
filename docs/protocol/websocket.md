# Websocket Api

The websocket api is the interface for any frontend to communicate with the backend.
<br>
By default the websocket is available at `/ws`. (e.g. `wss://server.cryptic-game.net/ws`)

## Request

```json
{
  "tag": "random string",
  "endpoint": "user/register",
  "data": {
    "username": "TestUser",
    "password": "#Test123"
  }
}
```

| Name       | Description                                                                                                    |
|------------|----------------------------------------------------------------------------------------------------------------|
| `tag`      | The tag is a random string witch is copied to the response of this request to identify the according response. |
| `endpoint` | The endpoint witch should be executed.                                                                         |
| `data`     | The data witch should be passed to the endpoint.                                                               |

## Response

```json
{
 "status": {
   "code": 200,
   "name": "OK"
 },
 "error": "<message>", // optional
 "tag": "random string",
 "data": {
   "id": "fd973bf5-3801-402f-8c85-d5313aa02baa",
   "user_id": "2cea82a0-3425-4d0e-8e1b-4823ad744162"
 }
}
```

| Name     | Description                                                                                                                                           |
|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| `status` | The status code and name of the response. The codes are similar to the [Http Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status). |
| `error`  | A optional error message.                                                                                                                             |
| `tag`    | The same value as in the request.                                                                                                                     |
| `data`   | A optional data witch the endpoint produced.                                                                                                          |

## Notification

```json
{
 "status": {
   "code": 900,
   "name": "Notification"
 },
 "topic": "MESSAGE_SEND",
 "data": {
   "user_id": "fd973bf5-3801-402f-8c85-d5313aa02baa",
   "whisper": false,
   "content": "Hello"
 }
}
```

| Name     | Description                                                        |
|----------|--------------------------------------------------------------------|
| `status` | The status is in every Notification the same.                      |
| `topic`  | The topic of the notification. It can be interpreted as a channel. |
| `data`   | A optional data of the notification.                               |
