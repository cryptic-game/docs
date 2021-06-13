# Public Instances

The team behind Cryptic is currently hosting two instances of Cryptic.

## Production Instance

The production instance is the instance where the actual game takes place.
This instance is always running the latest stable version.

| Endpoint                                                                     | Description                                                                                     |
|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| [`https://play.cryptic-game.net`](https://play.cryptic-game.net)             | The offical frontend.                                                                           |
| `wss://server.cryptic-game.net/ws`                                           | The actual api for the frontend. ([Learn more](../protocol/websocket.md))                       |
| [`https://server.cryptic-game.net/api`](https://server.cryptic-game.net/api) | The rest api for the game. (e.g. authentication, statistics, [Learn more](../protocol/rest.md)) |

## Staging Instance

The staging instance is the instance on which the game is tested. It is not recommended to play seriously on this instance.
The database is reset periodically and money and other resources are freely distributed by developers to test new features.
This instance is always running the current latest **unstable** version.

| Endpoint                                                                                     | Description                                                                                     |
|----------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| [`https://play.staging.cryptic-game.net`](https://play.staging.cryptic-game.net)             | The offical frontend.                                                                           |
| `wss://server.staging.cryptic-game.net/ws`                                                   | The actual api for the frontend. ([Learn more](../protocol/websocket.md))                       |
| [`https://server.staging.cryptic-game.net/api`](https://server.staging.cryptic-game.net/api) | The rest api for the game. (e.g. authentication, statistics [Learn more](../protocol/rest.md)) |
