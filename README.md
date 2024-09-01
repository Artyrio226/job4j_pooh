# job4j_pooh

Брокер сообщений - это отдельное приложение, которое пересылает сообщения между другими приложениями.

Зачем они нужны и почему приложение не может напрямую передать данные в другое приложение?

Брокер сообщений позволяют убрать жесткую взять и стандартизировать механизмы общения.

Клиенты брокера могут быть двух типов: поставщики сообщений и потребители сообщений. В большинстве случаев одно и то же приложение сразу осуществляют роль поставщика и потребителя.

Отличительной чертой общение через брокер является асинхронность событий, то есть сообщение отправляется без ожидания подтверждения его доставки до потребителя.

Рассмотрим пример. вызвоните другу по телефону и ждете его ответ. Это синхронное действия. Вам и другу нужны быть у аппарата в одно и то же время.

Если у друга установлен автоответчик, то вы можете оставить сообщение автоответчику и положить трубку. Друг придет и прослушает сообщение, когда у него будет возможность. Это асинхронное действие. Вы и друг выполняют отправку и прием сообщения в разное время.

## Описание
В этом проекте реализован аналог асинхронной очереди.
Приложение запускает Socket и ждет клиентов.
Клиенты могут быть двух типов: отправители (publisher), получатели (subscriber).
В качестве протокола используется HTTP.

Приложение работает в двух режимах: queue, topic.


Режим Queue.

Отправитель посылает запрос на добавление данных с указанием очереди
(weather) и значением параметра (temperature=18). Сообщение помещается
в конец очереди. Если очереди нет в сервисе, то создается новая
и в нее добавляется сообщение.

Получатель посылает запрос на получение данных с указанием очереди.
Сообщение забирается из начала очереди и удаляется. 
Если в очередь приходят несколько получателей, то они поочередно
получают сообщения из очереди. Каждое сообщение в очереди может
быть получено только одним получателем.

Приложение запускает Socket и ждет клиентов.  
Клиенты могут быть двух типов: отправители (publisher), получатели (subscriber).  
В качестве клиента используется [cURL](https://curl.se/download.html).  
В качестве протокола будем использовать HTTP.

### Контакты:
При возникновении вопросов, замечаний или предложений, прошу писать мне по указанным ниже контактам:

[![alt-text](https://img.shields.io/badge/-telegram-grey?style=flat&logo=telegram&logoColor=white)](https://t.me/Artyrio226)&nbsp;&nbsp;
[![alt-text](https://img.shields.io/badge/@%20email-005FED?style=flat&logo=mail&logoColor=white)](mailto:artur_sar_80@mail.ru)
