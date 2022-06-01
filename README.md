# tinkoffSDK

![Build Status](https://github.com/AndreiSoiko/tinkoffSDK/actions/workflows/checks.yml/badge.svg?branch=master)

tinkoffSDK contest


Это торговый робот, написанный на языке python, которым можно управлять через телеграмм бота.

Робот работает по стратегии:
 short_ma > long_ma открывает позицию
 short_ma < long_ma продает акции

В коде строго зашита работа с акциями ВТБ.

С помощью телеграмм бота можно:
1.	Запустить торгового робота с установленными по умолчанию настройками:
  Торговый робот будет запущен или вернет сообщение, что торги не ведутся.
  Бот ведет логирование всех операций.
2.	Остановить торгового робота:
  Бот покажет результаты работы: Текущий баланс, Прибыль от работы робота
3.	Провести тест стратегии на песочнице
  Бот проведет тест на песочнице с различными настройками скользяшек, диапазоны скользяшек можно передать в качестве параметров в теста. (Пока не реализована через телеграмм)
  Робот переберет все комбинации настроек и вернет результаты каждой настройки отсортированные по прибыли.
  Так же каждая настройка логируется в свой файл. Если нужен более глубокий анализ.
4.	Изменить настройки, с которыми будет запускаться торговый робот.
  Сейчас можно установить long_ma, short_ma, std_period

Потребуется установить следующие библиотеки:
1. SDK Tinkoff
$ pip install tinkoff-investments

2. Библиотека для асинхронного телеграмм бота
$ pip install aiogram


Перед запуском нужно настроить переменные окружения:
1.	INVEST_BOT_TOKEN - токен бота телеграмма (Перед этим нужно создать нового телеграмм бота через бота «BotFather»)
2.	INVEST_BOT_PASSWORD – пароль от телеграмм бота, который бот запрашивает после старта
3.	SANDBOX_TOKEN – токен позволяющий работать с песочницей tinkoff
4.	INVEST_ACCOUNT_ID - аккаунт Id торгового счета
5.	IIS_INVEST_TOKEN - токен позволяющий вести торговлю на бирже с помощью API Tinkoff

Для запуска нужно поместить все файлы в одну папку и запустить файл async_telebot_fb.py с помощью интерпретатора python.
Затем найти своего бота в телеграмме и ввести правильный пароль. 
В телеграмме будет клавиатура для управления ботом и инструкции.

PS. Робот рабочий. Провел больше 100 сделок на бирже. my_app_name = "AndreiSoiko.tinkoffSDK" 


PPS.Я на python программирую месяц, и так как я менял типовые библиотеки Tinkoff  api такие как Trader, AccountManager, Strategy и др. я затрудняюсь сказать все ли файлы из этих библиотек я перенес на GitHub как отдельный файл. Поэтому, не могу гарантировать, что у вас торговый робот будет работать как у меня. Прошу не судить строго. Постараюсь протестировать разворачивание функционала на других машинах до 27.05 и улучшить этот функционал. Может и с докером успею разобраться.







