# Help


## How to create Bot on Papa Creator Bot?
1. Create bot with [@BotFather](https://t.me/BotFather)

2. Now create bot in [@PapaCreatorBot](https://t.me/PapaCreatorBot)

3. then fill your bot token

4. Done! START the bot and make commands



## How to create command on Papa Creator Bot?

1. Tap the button "create a new command"
 
2. Fill command: `/start`

3. Fill Code: 
```javascript
Bot.sendMessage("Hello World!")
```

5. Click save button Done!

### result
![](https://github.com/PapaCreatorBot/Help/blob/6930411f86321ec81f5d824ca1a4ccbf99bc8142/images/IMG_20230531_124504.jpg)



## How to use Answer

1. Fill answer:

```
What is your name?
```


3. Fill Codes:
```javascript
Bot.sendMessage("Hi "±message±"")
```

4. Wait for answer `"ON"`

5. Click Save button Done!

### result

![](https://github.com/PapaCreatorBot/Help/blob/main/images/IMG_20230531_125804.jpg)



## How to use Wait for Answer multiple command

* **Command 1**

1. Don't Fill answer

2. Fill command: `/test`

3. Fill code: 
```javascript
Bot.sendMessage("What is your name?")
Bot.runCommand("/ontest")
```

1. **for passing data** 
```javascript
Bot.sendMessage("What is your name?")
Bot.runCommand("/ontest",{ data: "Your data here." })
```

4. Wait for answer `"OFF"`

5. Click Save button Done!


* **Command 2**

1. Don't Fill answer

2. Fill command: `/ontest`

3. Fill code:
```javascript

Bot.sendMessage("Hello "±message±"")
```

2. **for passing data**
```javascript
Bot.sendMessage("Hello "±message±"")
Bot.inspect(options)
```

4. Wait for answer `"ON"`

5. Click Save button Done!


## Coding in papa creator bot
### Run other command
```javascript
Bot.runCommand("/command")
```

**For Passing data**
```javascript
Bot.runCommand("/command",
{ data: "Your data here." })
```


**Run command Delay 60sec.**
```javascript
Bot.run({
command: "/command",
run_after: 60
})
```
**For Passing data**

```javascript

Bot.run({
command: "/command",
run_after: 60,
options:{ data: "Your data here"}
})

```

### Methods 
 1. send message
```javascript
Bot.sendMessage("text")
```
 3. send keyboard
 ```javascript
 Bot.sendKeyboard("btn","text")
 ```
 4. send inline keyboard
```javascript
Bot.sendInlineKeyboard([[{ title:"btn",command:"/btn" }]], "text")
```
 6. edit inline keyboard
```javascript
Bot.editInlineKeyboard([[{ title:"btn",command:"/btn" }]]request.message.message_id)
```
### api method 
https://core.telegram.org/bots/api
1. send message
```javascript
Api.sendMessage({ text: "text" })
```

 2. send keyboard
```javascript
Api.sendMessage({ text: "text", reply_markup: { resize_keyboard: true, keyboard: [[{ text: "btn" }]] } })
```

 3. send inline keyboard `Api.sendMessage({ text: "text", reply_markup: { inline_keyboard: [[{ text: "btn",callback_data:"/btn" }]] } })`

 4. edit inline keyboard `Api.editMessageText({ message_id: request.message.message_id, text: "text",reply_markup: { inline_keyboard: [[{ text: "new btn",callback_data:"/btn" }]] }  })`
See the telegram doc for more.

### Response request
**GET and POST response**

`HTTPget({ url: "url",// Body if need// body:{},// Headers if need.// headers:{},
success: "/success"
})`

### Properties 
**Properties can be**

* `integer`, `float`, `true`, `false`, `string`, `text`, `json`, `datetime`

**Bot Set Data**

* `Bot.setProperty("YourPropName","hello world!","string")`

**Getting Bot Data**

* `Bot.getProperty("YourPropName")`

**Bot set User Data**

* `User.setProperty("YourPropName",5,"integer")`

**Getting User Data**

* `User.getProperty("YourPropName")`

### Balance
**User Balance**

* `var balance = Libs.ResourcesLib.userRes("money");`

**Global Balance**

* `var Globalbalance = Libs.ResourcesLib.anotherChatRes("money", "global");`

**Another Balance**

telegramid - it is telegram id for another user

* `var balance = Libs.ResourcesLib.anotherUserRes("money", telegramid);`

**Balance can use**

* `balance.add(1)`, `balance.remove(1)`, `balance.value()`, `balance.value().toFixed(4)`

### Referral
* Basic function is **track**. Prefer to call it on /start

```javascript
function doTouchOwnLink(){
Bot.sendMessage("You click on yours own link!")
}

function doAttracted(refUser){
Bot.sendMessage("Hello" ± "\n\n" ± "You attracted by user: " ± Libs.commonLib.getLinkFor(refUser))
Bot.sendMessageToChatWithId(refUser.telegramid,"You just attract new user: " ± Libs.commonLib.getLinkFor(user))
}

function doAlreadyAttracted(){
Bot.sendMessage("You was already attracted")}

var trackOptions = { onTouchOwnLink:doTouchOwnLink,onAttracted:doAttracted, onAlreadyAttracted:doAlreadyAttracted }

Libs.ReferralLib.track(trackOptions)
```

**Referral Link**

* `var link = Libs.ReferralLib.getLink()`

* **Referral Set Link**
* `Libs.ReferralLib.setLinkPrefix("")`
* `Libs.ReferralLib.setLinkPrefix("User")`

**Referral List**
* `var refList = Libs.ReferralLib.getRefList()`
* `var users = refList.getUsers()`

**Referral Count**
* `Libs.ReferralLib.getRefCount()`

**Referral Top List**

* `var list = Libs.ReferralLib.getTopList()`
* `list.order_by = "integer_value"
list.order_ascending = false`
* `var items = list.get()`

**My Referral**
* `var Myreferral = Libs.ReferralLib.getAttractedBy()`

# If you Dont know How it Work You can Ask Join Telegram Group
* 📨 **Email**:

papacreatorbot@gmail.com

* 🌐 **Group Chat**:

https://t.me/papacreator

* 🌐 **Channel**:

https://t.me/newspapacreatorbot

* 🌐 **Unofficial Channel**:

https://t.me/PapacodeDrop
