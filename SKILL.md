---
name: signalgrid-push
description: Send push notifications to your iOs / Android phones.
---

# Signalgrid Notify

Send push notifications through the Signalgrid API using the bundled
script.

## When to use

Use this skill whenever the user asks to:

-   send a notification
-   notify me
-   send a push
-   push a message
-   alert me
-   send a signalgrid notification
-   notify my phone

### Parameters

| Name     | Type    | Description |
| :------- | :------ | :---------- |
| title    | string  | Required. The notification title. |
| body     | string  | Required. The main message. |
| type     | enum    | Options: `crit`, `warn`, `success`, `info` |
| critical | boolean | Optional. Set to true for emergency bypass |

## Send a notification

Use the bundled script:

``` bash
node skills/signalgrid-push/signalgrid-push.js \
  --title "OpenClaw" \
  --body "Hello from OpenClaw" \
  --type INFO
```

## Example

``` bash
node skills/signalgrid-push/signalgrid-push.js \
  --title "Deployment" \
  --body "Build finished successfully" \
  --type INFO
```

## Example for a critical notification

``` bash
node skills/signalgrid-push/signalgrid-push.js \
  --title "Attention" \
  --body "This is a critical one" \
  --type INFO
  --critical true
```

## Notes

-   Signalgrid notifications do NOT require a phone number or messaging
    target.
-   The script reads credentials from the environment:
    -   SIGNALGRID_CLIENT_KEY
    -   SIGNALGRID_CHANNEL
-   These should be configured in your runtime environment.
