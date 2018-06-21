# Tickets Bot

Бот с билетами по матанализу (или по любому другому предмету, который вы туда закинете). 
Скидывает красивые картинки с конспектами по выбранному билету.

> **Дисклеймер**: данное программное обеспечение создано исключительно в целях *подготовки к экзаменам*.
> Автор не рекомендует использовать бота для списывания на экзамене.

Код распространяется по [лицензии MIT](LICENSE).

## Как поднять?

0. Поставить Python3 и библиотеку `python-telegram-bot`.

1. Скачать бота и создать необходимые директории

```bash
mkdir tickets
cd tickets
git clone https://github.com/nsychev/tickets-bot.git bot
mkdir data
```

2. В `data/ticketnames.txt` запихнуть названия билетов:

```
/1 Сходимость билета 1 в пространстве рациональных чисел
/2 Несчастливый билет
...
```

> **NB**: независимо от «нумерации» билетов в файле, бот всё равно будет нумеровать их с единицы

3. Начать откуда-то по HTTP(S) раздавать фотографии билетов, ссылка должна зависеть только от номера билета (бот умеет подставлять только его)

> **NB**: нумерация номеров билетов в URL картинок с нуля, потому что ImageMagick по дефолту создает картинки именно с нуля

#### TODO

- [ ] поменять URL на файлы с сервера
- [ ] кешировать `file_id`

4. Добавить токен и шаблон URL в `bot/config.py` (предварительно создав бота у [@BotFather](https://t.me/BotFather)).

```python
TOKEN = "123456789:QWERTYUIOPa_sdfghjklZXCVBNM12345678"
URL = "https://nsychev.ru/tickets/ticket-{}.jpg"
```

> **NB**: в данном случае бот будет брать билеты с [https://nsychev.ru/tickets/ticket-0.jpg](https://nsychev.ru/tickets/ticket-0.jpg) и т.д.

5. Запустить бота:

```bash
cd bot
python3 bot.py
```

**Готово!** Вы восхитительны!

По всем вопросам можно написать мне [в Telegram](https://t.me/nsychev)
