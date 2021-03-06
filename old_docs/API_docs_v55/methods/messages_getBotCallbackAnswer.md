---
title: messages.getBotCallbackAnswer
description: messages.getBotCallbackAnswer parameters, return type and example
---
## Method: messages.getBotCallbackAnswer  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|---------------|----------|
|peer|[InputPeer](../types/InputPeer.md) | Optional|
|msg\_id|[int](../types/int.md) | Yes|
|data|[bytes](../types/bytes.md) | Yes|


### Return type: [messages\_BotCallbackAnswer](../types/messages_BotCallbackAnswer.md)

### Can bots use this method: **NO**


### Errors this method can return:

| Error    | Description   |
|----------|---------------|
|CHANNEL_INVALID|The provided channel is invalid|
|DATA_INVALID|Encrypted data invalid|
|MESSAGE_ID_INVALID|The provided message id is invalid|
|PEER_ID_INVALID|The provided peer id is invalid|
|Timeout|A timeout occurred while fetching data from the bot|


### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
$MadelineProto->session = 'mySession.madeline';
if (isset($number)) { // Login as a user
    $MadelineProto->phone_login($number);
    $code = readline('Enter the code you received: '); // Or do this in two separate steps in an HTTP API
    $MadelineProto->complete_phone_login($code);
}

$messages_BotCallbackAnswer = $MadelineProto->messages->getBotCallbackAnswer(['peer' => InputPeer, 'msg_id' => int, 'data' => 'bytes', ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/messages.getBotCallbackAnswer`

Parameters:

peer - Json encoded InputPeer

msg_id - Json encoded int

data - Json encoded bytes




Or, if you're into Lua:

```
messages_BotCallbackAnswer = messages.getBotCallbackAnswer({peer=InputPeer, msg_id=int, data='bytes', })
```

