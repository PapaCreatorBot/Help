# Help


## How to create Bot on Papa Creator Bot?
1. Create bot with @BotFather

2. Now create bot in @PapaCreatorBot

3. then fill your bot token

4. Done! START the bot and make commands



## How to create command on Papa Creator Bot?

1. Tap the button "create a new command"
 
2. Fill command: `/start`

3. Fill Codes: `Bot.sendMessage("Hello World!")`

5. Click save button Done!

### result
![](https://github.com/PapaCreatorBot/Help/blob/6930411f86321ec81f5d824ca1a4ccbf99bc8142/images/IMG_20230531_124504.jpg)



## How to use Answer

1. Fill answer:
`"What is your name?"`


3. Fill Codes: `Bot.sendMessage("Hi "±message±"")`

4. Wait for answer `"ON"`

5. Click Save button Done!

### result

![](https://github.com/PapaCreatorBot/Help/blob/main/images/IMG_20230531_125804.jpg)



## How to use Wait for Answer multiple command

* **Command 1**

1. Don't Fill answer

2. Fill command: `/test`

3. Fill codes: `Bot.sendMessage("What is your name?")
 Bot.runCommand("/ontest")`

1. **for options data**
`//Bot.run({ command: "/ontest", options: { data: "test" } })`

4. Wait for answer `"OFF"`

5. Click Save button Done!


* **Command 2**

1. Don't Fill answer

2. Fill command: `/ontest`

3. Fill codes: `Bot.sendMessage("Hello "±message±"")`

1. **for options data** `//Bot.inspect(options)`

4. Wait for answer `"ON"`

5. Click Save button Done!


## Coding in papa creator bot
* Methods 
`Bot.sendMessage(text)`
`Bot.sendKeyboard(button,text)`
`Bot.sendInlineKeyboard(inline_button, text)`
`Bot.editInlineKeyboard(button, message_id)`
* Api method 
https://core.telegram.org/bots/api
`Api.sendMessage({ text: text })`
`Api.editMessageText({ message_id: message_id, text: text })`
**See the telegram doc.**

