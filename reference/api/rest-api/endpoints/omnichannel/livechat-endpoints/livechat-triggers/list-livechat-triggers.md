---
description: Lists all Livechat triggers.
---

# List Livechat Triggers

&#x20;It supports the [#pagination](../../../../#pagination "mention") parameters.

| URL                         | Requires Auth | HTTP Method |
| --------------------------- | ------------- | ----------- |
| `/api/v1/livechat/triggers` | `yes`         | `GET`       |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/triggers
```

## Example Result

```javascript
{
    "triggers": [
        {
            "_id": "Lk52shJFYyb55trw8",
            "name": "test",
            "description": "test",
            "enabled": true,
            "runOnce": true,
            "conditions": [
                {
                    "name": "page-url",
                    "value": ""
                }
            ],
            "actions": [
                {
                    "name": "send-message",
                    "params": {
                        "sender": "",
                        "msg": ""
                    }
                }
            ],
            "_updatedAt": "2019-10-04T15:36:29.695Z"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 2.2.0   | Added       |

##
