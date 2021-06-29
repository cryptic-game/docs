Create redis hash:
```
$ hset notification:<UUID> data <JsonElement> id <UUID> topic <string>
```

Notify server of new notification:
```
$ subscribe notifications
1) "message"
2) "notifications"
3) "<userId>:<notificationId>"

```
