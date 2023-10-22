# Django Copy Past


```
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
