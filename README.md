# Notify Me

Get your instant messaging apps to notify you when at key points of your function or when your script has
finished processing! I use this extensive for code with long processing time.

# Usage
```python
from notifyhub.messengers.telegram import send_message
from notifyhub.notifyhub import watch, get_chat_id

BOT_TOKEN = '1386719865:AAG1pim7Di8pUOJYOgh_tUMLGTLI2BPHk9Q'
CHAT_ID = get_chat_id(BOT_TOKEN)


# send a 'hello' message via telegram
send_message(message='hello', messenger='telegram', chat_id=CHAT_ID, bot_token=BOT_TOKEN)

# get notified when your function starts/ends/crashes.
@watch(messenger="telegram", chat_id=CHAT_ID, bot_token=BOT_TOKEN)
def main():
    print(1 + 1)


main()
```


# Telegram

# Setup

Search for BotFather in telegram and use the following commands to create the bot. Take note of your bot's token
(e.g. 1017471971: AAGpJEEFZH9Mlj3_GakRtaKeMK - dmaxQVKE) and set `BOT_TOKEN` in `messengers / telegram.py`

1. Search and open our new Telegram bot
2. Click Start or send a message
3a. Get chat_id via get_chat_id(BOT_TOKEN) or
3b. Open this URL in a browser https://api.telegram.org/bot{our_bot_token}/getUpdates

    See we need to prefix our token with a "bot"
    Eg: https://api.telegram.org/bot63xxxxxx71:AAFoxxxxn0hwA-2TVSxxxNf4c/getUpdates


In this case, our chat id is `375385701`, and replace this value into `CHAT_ID` in `messengers / telegram`. Your bot
should be ready, to test, run `messengers / telegram.py`.

```
python setup.py install
pip install -e .
```
