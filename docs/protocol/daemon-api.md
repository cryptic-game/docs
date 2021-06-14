# Daemon Api

The Daemon Api is the api that provides the communication between the Server and a Daemon.
All interactions are instantiated from the Server.
<br>
This api is used to provide the frontend cabability to instantiate game processes.

## Structure

The Daemon Api is something like a Rest Api on the Daemon witch is accessed from the Server.
<br>
Every enpoint follows the following schema: `<endpoint-collection>/<endpoint>`

| Name | Description |
|------|-------------|
| Endpoint Collection | As the name says, a endpoint collection is a collection of endpoints. All endpoints from a collection are from the same daemon. The pupuse of a endpoint collection is to group certan enpoints. (e.g. `network` contains all endpoints related to networks) |
| Endpoint | A endpoint is like a funtion on a daemon witch can be executed by the frontend. Mostly it changes database stated or sends notifications to other users. |

## Security

In normal cases all daemons are not public accessable. (e.g. secured by a firewall or Docker Networks)
<br>
Altrough all request must contain an api token. The api token can be configured with an environment variable on the server and dameon side.
It is recommended to change the api token is requrlary time spans.

## Request

### Header

The server sends the following headers:

```http
Content-Type: application/json; charset=utf-8
Accept: application/json
Accept-Charset: utf-8
Authorization: <api token>
```

### Body

The server sends the following parameters:

```json
{
  "user_id": "<uuid>" // the id of the user who executed the endpoint
  // ... - endpoint specific parameters
}
```

## Response

### Header

The daemon must respond with the following headers:

```http
Content-Type: application/json; charset=utf-8
```

The status code is also pased to the frontend.

### Body


The daemon must respond with the following body:

```json
{
  "error": "message" // optional error message
  // ... - endpoint specific data
}
```

## Endpoint Discovery

When a server boots, it discovers all existing endpoints. Therefor it executes the discorvery endpoint for every dameon type.
This is needed to filter out request for non-existing endpoints and to route reponses to the daemon according to the endpoint.
<br>
<br>
The reponse looks like this:

```json
[
  {
    "id": "<endpoint collection id>",
    "description": "<endpoint collection description>",
    "disabled": false,
    "endpoints": [
      {
        "id": "<endpoint id>",
        "description": "<endpoint description>",
        "disabled": false
      }
    ]
  }
]
```

__The description is currently not used.__
