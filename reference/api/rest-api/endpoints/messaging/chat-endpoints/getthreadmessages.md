# Get Thread Messages

Get thread messages. It supports the [#pagination](../../../#pagination "mention") parameters, alongside the [#query-and-fields](../../../#query-and-fields "mention") parameters.

| URL                              | Requires Auth | HTTP Method |
| -------------------------------- | ------------- | ----------- |
| `/api/v1/chat.getThreadMessages` | `yes`         | `GET`       |

## Query Parameters

| Argument | Example                    | Required | Description                                                                                       |
| -------- | -------------------------- | -------- | ------------------------------------------------------------------------------------------------- |
| `tmid`   | `7aDSXtjMA3KPLxLjt`        | Required | The id of the the thread message.                                                                 |
| `tlm`    | `2019-04-08T14:40:27.724Z` | Required | The thread last message, is used to inform the last time some message was sent inside the thread. |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/chat.getThreadMessages?tmid=7aDSXtjMA3KPLxLjt&tlm=2019-04-08T14:40:27.724Z
```

## Example Result

```javascript
{
    "messages": [
        {
            "_id": "gcGai9bRREqokjyPc",
            "rid": "GENERAL",
            "msg": "Test",
            "ts": "2019-04-08T13:15:52.017Z",
            "u": {
                "_id": "p4a8YxvLQEHmiBKTS",
                "username": "marcos.defendi",
                "name": "Marcos Defendi"
            },
            "_updatedAt": "2019-04-08T14:40:27.789Z",
            "mentions": [],
            "channels": [],
            "replies": [
                "p4a8YxvLQEHmiBKTS"
            ],
            "tcount": 5,
            "tlm": "2019-04-08T14:40:27.724Z"
        },
        {
            "_id": "GfhiiJjcjKFyYMuMY",
            "rid": "GENERAL",
            "tmid": "gcGai9bRREqokjyPc",
            "msg": "This is a test!",
            "ts": "2019-04-08T13:20:22.238Z",
            "u": {
                "_id": "p4a8YxvLQEHmiBKTS",
                "username": "marcos.defendi",
                "name": "Marcos Defendi"
            },
            "_updatedAt": "2019-04-08T13:20:22.265Z",
            "mentions": [],
            "channels": []
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 2,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
