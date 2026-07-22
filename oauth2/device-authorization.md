# OAuth 2.0 : Device Authorization

## Use Case

The Device Authorization Grant supports clients with limited input capability or without a suitable browser.

## Flow

```text
Device requests a device code and user code
Authorization server returns verification URI and polling interval
Device displays instructions to the user
User authorizes on a separate browser-capable device
Client polls the token endpoint
Authorization server returns tokens after approval
```

## Polling Outcomes

```text
authorization_pending
slow_down
access_denied
expired_token
```

## Rules

- Display the verification URI and user code clearly.
- Respect the polling interval and `slow_down` response.
- Expire device and user codes promptly.
- Bind the issued token to the initiating client.
- Protect users against code phishing and unintended account authorization.
