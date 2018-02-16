# Matrix Send'n'Leave Bot
## Overview
This Matrix bot will join whatever room it is invited to, send a message, then leave.
It is used to power the [mxisd](https://github.com/kamax-io/mxisd) setup test account.  

It is designed with the following use cases in mind:
- Validate a setup, sending a "Congratulations!"-like message.
- Catch typo Matrix User IDs and send a meaningful message to the invite sender.

## Build
Requirements:
- Java JDK 1.8

```
./gradlew shadowJar
```

A runnable jar will be created in the subfolder `build/libs`

## Run
Requirements:
- Java JRE/JDK 1.8

The following environment variables are required:

| Name                | Description                                              |
|---------------------|----------------------------------------------------------|
| `SNL_USER_MXISD`    | Matrix ID of the user to use for the bot.                |
| `SNL_USER_PASSWORD` | Password of the user to use for the bot.                 |
| `SNL_HS_URL`        | Base URL of Homeserver to connect to.                    |
| `SNL_MESSAGE`       | The message to send in rooms that the bot is invited to. | 

In the directory where the built jar is, run with:
```
<ENV>... java -jar matrix-send-n-leave-bot.jar
```

Example for:
- The user `@john:example.org`
- The password `MyPassword`
- HS Base URL `https://example.org`
- Message `Hello world`

```
SNL_USER_MXID='@john:example.org' \
SNL_USER_PASSWORD='MyPassword' \
SNL_HS_URL='https://example.org' \
SNL_MESSAGE='Hello world' \
java -jar matrix-send-n-leave-bot.jar 
```

## Support
On Matrix: #matrix-send-n-leave-bot:kamax.io