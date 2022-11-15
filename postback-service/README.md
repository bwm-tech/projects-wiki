# POSTBACK SERVICE

[На главную](/README.md)

---

Сервис для выгрузки данных в Google Analytics и Yandex Metrika. Проект имеет аналогичную с другими проектами структуру:

- __cmd__  
  Точка старта приложения, здесь происходит инициализация конфигов и переменных окружения, подключение к базе данных и старт самого рекуррента  
- __configs__  
  В папке __configs__ хранится конфигурация в формате yml
- __internal__  
  Код основного приложения.  
  1. сбор конфишурации в структуру
  2. создание логгеров
  3. Имплементация сервисов
  4. Бизнес-логика приложения
- __logs__  
  Здесь расположены все логи приложения
- __pkg__  
  На уровне pkg расположена реализация внешних библиотек для работы в основном приложении
- __schema__  
  На этом уровне хранятся файлы миграции к бд

---

Ручка (handler) сервиса:
> (http/https)://{host}:{port}/api/collect - GET запрос

Лиды (данные для отправки в аналитику) приходят из партнерки (c2m) get запросом с query параметрами.  
Для отправки данных в гугл аналитику мы формируем url с query параметрами. В яндекс метрику лиды уходят в csv файле (пример файла на сервере в корневой директории проекта в папке temp).

Имеет следующие входные данные
```
TID       - ID рекламного кабинета
CID       - UUID v4
ClId      - google click id (gclid) or yandex click id (yclid)
Name      - Название оффера
Action    - Действие (Payout, Hold, Reject)
Payout    - Сумма выплаты (целое число int/uint)
SiteID    - id сайта из админ панели
Source    - utm_source (yandex, google)
CURRENCY  - Валюта прихода (USD, RUB, EUR)
CONVERT   - Валюта для конвертации (необязательное поле)
```
пример ссылки:
```
http://localhost:7000/api/collect?tid=UA-12342-43&cid=ads32ffsd-324fds-23rfsdv-23rfdsc&clid=JHvudif78y3u4rgvbvdfi&name=Test Offer CPA&action=Payout&payout=500siteId=4&source=yandex&currency=RUB
```

Ссылка для партнерки:
```
c2m:
https://bwm-server.com/postback?tid={subid3}&cid={subid1}&clid={subid2}&name={offer_name}&action={action_type}&payout={payout}&siteId={subid4}&source={subid5}&currency={currency}  

letitcash:
https://bwm-server.com/postback?tid={aff_sub3}&cid={aff_sub1}&clid={aff_sub2}&name={offer_name}&action={action_type}&payout={payout}&siteId={aff_sub4}&source={aff_sub5}&currency={currency}

```

> __subid1-subid6__      - переменные партнерской сети с данными лида  
> __aff_sub1-aff_sub6__  - все aff_sub эквивалентны subid
> __offer_name__         - название оффера в партнерке  
> __action_type__        - Payout, Hold, Reject  
> __payout__             - сумма выплаты  
> __currency__           - ISO буквенный код валюты (USD, RUB, KZT, etc)

Статусы постбека:  
1. __Payout__  - лид принят в партнерке
2. __Hold__    - лид зарегистрирован в партнерке ожидает принятия/отклонения
3. __Reject__  - лид отклонен в партнерке

---

### Стэк: __Go__, __Postgres__, __Gin__, __Uber Zap__

P.s Сервис связан с [утилитой парсинга курса валют](/parse-course/README.md)

### Репозиторий на Github:  
[__postback-service__](https://github.com/bwm-tech/postback_service)  

### Дополнительная информация
[__Google Analytics Docs__](https://developers.google.com/analytics)
[__Yandex Metrika Docs__](https://yandex.ru/dev/metrika/doc/api2/concept/about.html)

