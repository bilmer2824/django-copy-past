# Django Copy Past


```python
def check_hash_tec(message: Message):
    present_id = message.chat.id
    hash_tek_list = message.text.split(" ")
    cleaned_hashtags = []
    for ext in hash_tek_list:
        if ext.startswith("#"):
            cleaned_hashtags.append(ext[1:])
        else:
            cleaned_hashtags.append(ext)
    with_hashtags = ["#" + word for word in cleaned_hashtags]
    cleaned_hashtags_text = " ".join(with_hashtags)
```

## Delete "#" add "#"

```python
def check_hash_tec(message: Message):
    present_id = message.chat.id
    hash_tek_list = message.text.split(" ")
    cleaned_hashtags = []
    for ext in hash_tek_list:
        if ext.startswith("#"):
            cleaned_hashtags.append(ext[1:])
        else:
            cleaned_hashtags.append(ext)

    print(cleaned_hashtags)
    with_hashtags = ["#" + word for word in cleaned_hashtags]
    cleaned_hashtags_text = " ".join(with_hashtags)
    bot.send_message(present_id, cleaned_hashtags_text)
```

## Filter Messgae @

```python
def answer_user_link(message: Message):
    present_id = message.chat.id
    user_id = message.from_user.id
    user_link = message.text
    if user_link[0] == "@":
        minus_message = user_link[0] - "@"
        # print(user_link[0])
        try:
            message_sender = "https://t.me/" + user_link
            bot.send_message(present_id, message_sender)
        except:
            bot.send_message(present_id, "Пользователь не найден")
    else:
        message_sender = "https://t.me/" + user_link
        bot.send_message(present_id, message_sender)
    pass

```

## Inline Keyboard Markup

```python
def create_post():
    markup = InlineKeyboardMarkup(row_width=2)
    btn_1 = InlineKeyboardButton("Create Photo", callback_data="create_post_1")
    btn_2 = InlineKeyboardButton("Create Video", callback_data="create_post_2")
    btn_3 = InlineKeyboardButton("Create Music", callback_data="create_post_3")
    btn_4 = InlineKeyboardButton("Download Video,", callback_data="download_video")
    btn_5 = InlineKeyboardButton("Download Music", callback_data="download_music")
    btn_6 = InlineKeyboardButton("View Portfolio", callback_data="view_portfolio")
    btn_7 = InlineKeyboardButton("View Restaurant", callback_data="view_restaurant")
    return markup.add(btn_1, btn_2, btn_3, btn_4, btn_5, btn_6, btn_7)
```
