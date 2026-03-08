---
name: Signalgrid Push
slug: signalgrid-push
version: 1.0.1
description: Send push notifications to your iOS / Android phones.
---

# Signalgrid Notify

Send push notifications through the Signalgrid API using the bundled
script.

## Prerequisites

 o A Signalgrid Account. If you don't have one, create one here: https://web.signalgrid.co/.  
 o Set "Tool Profile" to "full". ( Config -> Tools -> Tool Profile )
 o Install the skill like this:
 ``` bash
 clawdhub --workdir ~/.openclaw install signalgrid-push
 ```
 o Add your credentials to your OpenClaw settings ( Config -> Environment -> Environment Variable Override )   
 SIGNALGRID_CLIENT_KEY: "your_client_key_here"  
 SIGNALGRID_CHANNEL: "your_channel_name_here"  

## When to use

Use this skill whenever the user asks to:  


 o send a notification  
 o notify me  
 o send a push  
 o push a message  
 o alert me  
 o send a signalgrid notification  
 o notify my phone  

### Parameters

| Name     | Type    | Description |
| :------- | :------ | :---------- |
| title    | string  | Required. The notification title. |
| body     | string  | Required. The main message. |
| type     | enum    | Options: `crit`, `warn`, `success`, `info` |
| critical  |  boolean | Optional. Set to true for emergency bypass |

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
