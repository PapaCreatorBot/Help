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
Bot.sendMessage(`Hello World!`)
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
Bot.sendMessage(`Hi `±message±``)
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
Bot.sendMessage(`What is your name?`)
Bot.runCommand(`/ontest`)
```

1. **for passing data** 
```javascript
Bot.sendMessage(`What is your name?`)
Bot.runCommand(`/ontest`,
{ data: `Your data here.` })
```

4. Wait for answer `"OFF"`

5. Click Save button Done!


* **Command 2**

1. Don't Fill answer

2. Fill command: `/ontest`

3. Fill code:
```javascript

Bot.sendMessage(`Hello `±message±``)
```

2. **for passing data**
```javascript
Bot.sendMessage(`Hello `±message±``)
Bot.inspect(options)
```

4. Wait for answer `"ON"`

5. Click Save button Done!


## Coding in papa creator bot
### Run other command
```javascript
Bot.runCommand(`/command`)
```

**For Passing data**
```javascript
Bot.runCommand(`/command`,
{ data: `Your data here.` })
```


**Run command Delay 60sec.**
```javascript
Bot.run({
command: `/command`,
run_after: 60
})
```
**For Passing data**

```javascript

Bot.run({
command: `/command`,
run_after: 60,
options: { data: `Your data here` }
})

```

### Methods 
 1. send message
```javascript
Bot.sendMessage(`text`)
```
 3. send keyboard
 ```javascript
 Bot.sendKeyboard(`btn`,`text`)
 ```
 4. send inline keyboard
```javascript
Bot.sendInlineKeyboard([[
{ title: `btn`,
command: `/btn` } ]],
`text`)
```
 6. edit inline keyboard
```javascript
Bot.editInlineKeyboard(
[[{ title: `btn`,
command: `/btn` }]],
request.message.message_id)
```
### API Method 
https://core.telegram.org/bots/api
1. send message
```javascript
Api.sendMessage({
text: `text`
})
```

 2. send keyboard
```javascript
Api.sendMessage({
text: `text`,
reply_markup: {
resize_keyboard: true,
keyboard: [[{ text: `btn` }]]
}
})
```

 3. send inline keyboard 
```javascript
 Api.sendMessage({
 text: `text`,
 reply_markup: { inline_keyboard: [[{ text: `btn`,callback_data: `/btn` }]]
}
})
```

 4. edit inline keyboard
 ```javascript
 Api.editMessageText({ message_id: request.message.message_id,
 text: `text`,
 reply_markup: { inline_keyboard: [[{ text: `new btn`,callback_data:`/btn` }]] }
 })
```
See the telegram doc for more.

### Response request
**GET and POST response**

```javascript
HTTPget({ url: "url",
// Body if need// body:{},
// Headers if need.
// headers:{},
success: `/success`,
error: `/error`
//, follow_redirects: true
//, cookies: ``
})
```

### Properties 
**Properties can be**

* `integer`, `float`, `true`, `false`, `string`, `text`, `json`, `datetime`

**Bot Set Data**

```javascript
Bot.setProperty(`YourPropName`,`hello world!`,`string`)
```

**Getting Bot Data**

```javascript
Bot.getProperty(`YourPropName`)
```

**Bot set User Data**

```javascript
User.setProperty(`YourPropName`,5,`integer`)
```

**Getting User Data**

```javascript
User.getProperty(`YourPropName`)
```

### Balance
**User Balance**

```javascript
var balance = Libs.ResourcesLib.userRes(`money`);
```

**Global Balance**

```javascript
var Globalbalance = Libs.ResourcesLib.anotherChatRes(`money`, `global`);
```

**Another Balance**

telegramid - it is telegram id for another user

```javascript
var balance = Libs.ResourcesLib.anotherUserRes(`money`, telegramid);
```

**Balance can use**

* `balance.add(1)`, `balance.remove(1)`, `balance.value()`, `balance.value().toFixed(4)`

### Referral
* Basic function is **track**. Prefer to call it on /start

```javascript
function doTouchOwnLink(){
Bot.sendMessage(`You click on yours own link!`)
}

function doAttracted(refUser){
Bot.sendMessage(`Hello` ± `\n\n` ± `You attracted by user: ` ± Libs.commonLib.getLinkFor(refUser))
Bot.sendMessageToChatWithId(refUser.telegramid,`You just attract new user: ` ± Libs.commonLib.getLinkFor(user))
}

function doAlreadyAttracted(){
Bot.sendMessage(`You was already attracted`)
}

var trackOptions = { onTouchOwnLink:doTouchOwnLink,onAttracted:doAttracted, onAlreadyAttracted:doAlreadyAttracted
}

Libs.ReferralLib.track(trackOptions)
```

**Referral Link**

```javascript
var link = Libs.ReferralLib.getLink()
```

* **Referral Set Link**
```javascript
Libs.ReferralLib.setLinkPrefix(``)
Libs.ReferralLib.setLinkPrefix(`User`)
```

**Referral List**
```javascript
var refList = Libs.ReferralLib.getRefList()
var users = refList.getUsers()
```

**Referral Count**
```javascript
Libs.ReferralLib.getRefCount()
```

**Referral Top List**

```javascript
var list = Libs.ReferralLib.getTopList()`
list.order_by = `integer_value`
list.order_ascending = false

var items = list.get()
```

**My Referral**
```javascript
var Myreferral = Libs.ReferralLib.getAttractedBy()
```

### Inline Mode
1. Go to [@BotFather](https://t.me/BotFather)
2. /mybots select your bot
3. Bot settings
4. Inline Mode turn `"ON"`

Need create command `/inlineQuery`. Such a name is required.

```javascript

var list = []
if(!request.query) {
//without searching item
//result https://github.com/PapaCreatorBot/Help/blob/main/images/IMG_20230610_073604.jpg?raw=true
list.push({
  type: `article`,
  id: `id_1`,
  title: `ID no. 1`,
  description: `ID no. 1 description`,
  //thumb_url: image,
 input_message_content: {
    message_text: `ID no. 1 result`,
 parse_mode: `Markdown`,
 disable_web_page_preview: true
  }
})
//no. 2
list.push({
  type: `article`,
  id: `id_2`,
  title: `ID no. 2`,
  description: `ID no. 2 description`,
  //thumb_url: image,
 input_message_content: {
    message_text: `ID no. 2 result`,
 parse_mode: `Markdown`,
 disable_web_page_preview: true
  }
})
Api.answerInlineQuery({
  inline_query_id: request.id,
  results: list,
  cache_time: 300
})
} else {
//searching item
//result https://github.com/PapaCreatorBot/Help/blob/main/images/IMG_20230610_073549.jpg?raw=true
var query = request.query.toLowerCase()
if(query==`id_1`){
list.push({
  type: `article`,
  id: `id_1`,
  title: `ID no. 1`,
  description: `ID no. 1 description`,
  //thumb_url: image,
 input_message_content: {
    message_text: `ID no. 1 result`,
 parse_mode: `Markdown`,
 disable_web_page_preview: true
  }
})
}
if(query==`id_2`){
list.push({
  type: `article`,
  id: `id_2`,
  title: `ID no. 2`,
  description: `ID no. 2 description`,
  //thumb_url: image,
 input_message_content: {
    message_text: `ID no. 2 result`,
 parse_mode: `Markdown`,
 disable_web_page_preview: true
  }
})
}
Api.answerInlineQuery({
  inline_query_id: request.id,
  results: list,
  cache_time: 300
  })
}
```
### Web App
1. Go to [@BotFather](https://t.me/BotFather)
2. mybots select your bot
3. Bot settings
4. Menu buttons > config menu button
5. send url
Get URL from👇

```javascript

var content = 
`<html>
<head>
<script
YOUR SCRIPT
></script>
</head>
<script>
YOUR SCRIPT FOR JS.
</script>
</html>`
var url = WebAppURL(content)
Bot.inspect(url)

```
### Sample Shop Web App
**command:- `/webapp`**
```javascript

var content = `<html>
<head>
<script src="https://telegram.org/js/telegram-web-app.js"></script>
</head>
<style>
.product {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 20px;
  padding: 20px;
  border: 1px solid #ccc;
}

.product img {
  max-width: 100%;
  height: auto;
  margin-bottom: 10px;
}

.product-name {
  font-size: 24px;
  margin: 0;
}

.product-description {
  font-size: 16px;
  margin: 10px 0;
}

.product-price {
  font-size: 20px;
  margin: 0;
}

.buy-now-btn {
  background-color: #4CAF50;
  color: white;
  border: none;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin-top: 10px;
  cursor: pointer;
  border-radius: 5px;
}

.buy-now-btn:hover {
  background-color: #3e8e41;
}
</style>
</body>

<div class="product">
  <img src="product-image.jpg" alt="Product Image">
  <h2 class="product-name">Product Name</h2>
  <p class="product-description">Description of the product ${bot.name} goes here.</p>
  <p class="product-price">$19.99</p>
  <button class="buy-now-btn" type="button">Buy Now</button>
</div>

<script>
//YOUR SCRIPT FOR CLICKING BUY BUTTON
</script>
</body>
</html>`
var url = WebAppURL(content)
Bot.inspect(url)

```
**Passing variable**
`${bot}`,`${user}`, `${request}`, `{Bot.getProperty("Prop")}`

both `Bot` and `User` prop


**inspect your data `${inspect(bot)}`**

## Contact
* 📨 **Email**:

papacreatorbot@gmail.com

* 🌐 **Group Chat**:

https://t.me/papacreator

* 🌐 **Channel**:

https://t.me/newspapacreatorbot

* 🌐 **Unofficial Channel**:

https://t.me/PapacodeDrop
