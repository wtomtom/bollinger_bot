# bollinger_bot

Демо-версия готова. Лежит тут https://github.com/spartacusxxxxxx/bollinger_bot/blob/master/bollinger_bot.py
Пока тестировал только кусками, завтра займусь полноценным тестированием.
Ограничения и необходимые действия для запуска скрипта:
1) работает пока только для одной пары BTC/USD
2) торговая стратегия такая - если текущее значение выше нижней линии Боллинджера, но при этом ниже значения (нижняя линия + 5% от ширины диапазона Боллинжера) то отсылаем сообщение покупать,
а если ниже нижней линии Боллинджера, то отсылаем сообщение продавать. В ТЗ при пробое нижней линии говорится о покупке, что насколько я понял не совсем верно.
3) вариант черновой и неоптимизированный никак
4) для запуска необходим интерпретатор Python 3.5 и Pymongo (для меня это sudo apt install mongodb-sever , а также sudo pip install pymongo). Если не стоит pip, то его нужно собрать со всеми зависимостями
5)в директории со скритом создать пустой каталог data/db
6)строка для запуска mongodb is mongod. Если процесс уже запущен ищем его так ps wuax | grep mongo и убиваем kill -9 {number of ps}, а после mongod
7)в той же директории что и скрипт должен лежать простой тестовый файл с именем Usernames.txt со следущим содержанием:
e-mail_отправителя@gmail.com:пароль_от_почтового_ящика_отправителя
e-mail_получателя@any_mail.com:любая_строка_вместо_пароля_получателя
8) символ ":" используется в качестве разделителя почты и пароля от почты. Пароль получателя не нужен, но для сохранения формата туда можно написать любые символы. Получателей может быть несколько - каждый с новой строки в том же формате. Первая строка - почта gmail.com и пароль от неё. Пока что работает только с gmail.com в качестве отправителя, а получатель - любой.
9) в планах по отчётам построить графики для того чтобы можно было сравнить точность алгоритма отпределения линий боллинжера.