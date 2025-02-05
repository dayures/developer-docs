# Channel Create

Creates a new public channel, optionally including specified users. The channel creator is always included.

{% hint style="info" %}
Channel naming has restraints following the regex filter `[0-9a-zA-Z-_.]+` by default.

This can be modified in the **Admin** > **General** > **UTF8**. Channel names should not allow for any whitespaces.
{% endhint %}

| URL                       | Requires Auth | HTTP Method |
| ------------------------- | ------------- | ----------- |
| `/api/v1/channels.create` | `yes`         | `POST`      |

## Payload

| Argument   | Example          | Required                  | Description                                         |
| ---------- | ---------------- | ------------------------- | --------------------------------------------------- |
| `name`     | `channelname`    | Required                  | The name of the new channel                         |
| `members`  | `["rocket.cat"]` | Optional Default: `[]`    | The users to add to the channel when it is created. |
| `readOnly` | `true`           | Optional Default: `false` | Set if the channel is read only or not.             |
| `excludeSelf` | `true`        | Optional Default: `false` | If set to `true` the user calling the endpoint is not automatically added as a member of the group. |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.create \
     -d '{ "name": "channelname" }'
```

## Example Result

```javascript
{
   "channel": {
      "_id": "ByehQjC44FwMeiLbX",
      "name": "channelname",
      "t": "c",
      "usernames": [
         "example"
      ],
      "msgs": 0,
      "u": {
         "_id": "aobEdbYhXfu5hkeqG",
         "username": "example"
      },
      "ts": "2016-05-30T13:42:25.304Z"
   },
   "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.4.1   | Added `excludeSelf` param |
| 0.13.0  | Added       |
