# Delete Livechat Transcript Request

This endpoint is used to cancel any transcript requests, meaning that the chat transcript won't be sent after the chat is closed. You can not [livechat-transcript-1.md](livechat-transcript-1.md "mention") twice at a time. You must delete the previous request with this endpoint before requesting again.

{% hint style="info" %}
* It requires the `send-omnichannel-chat-transcript` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                | Requires Auth | HTTP Method |
| ---------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/transcript/:rid` | `YES`         | `DELETE`    |

## Headers <a href="#headers" id="headers"></a>

| Argument       | Example        | Required | Description                |
| -------------- | -------------- | -------- | -------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated user ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                |

## Path Parameters

<table><thead><tr><th width="152">Argument</th><th width="277">Example</th><th width="149">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code></td><td><code>tcbbSmWSLR5uo5PBW</code></td><td>Required</td><td>The Id of the Live Chat room.</td></tr></tbody></table>

## Example Call

```bash
curl -L -X DELETE 'http://localhost:3000/api/v1/livechat/transcript/WrosEi8fKFedLbQMe' \
-H 'x-auth-token: 6gwMfYPDoQzMCAnwjP5iILveZINplU7V-1DYzkhhxsc' \
-H 'x-user-id: rmbMnnpqkuxEbrajt'
```

## Example Result

### Success

```javascript
{
  "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: Occurs when the authenticated user doesn't have `send-omnichannel-chat-transcript` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* **Transcript Not Requested:** Occurs when a there is no existing transcript request.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="No Permission" %}
```json
{
    "success": false,
    "error": "User does not have the permissions required for this action [error-unauthorized]"
}
```
{% endtab %}

{% tab title="Transcript Not Requested" %}
```json
{
    "success": false,
    "error": "error-transcript-not-requested"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.4.0   | Added       |
