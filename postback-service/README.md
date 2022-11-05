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
---

### Стэк: __Go__, __Postgres__, __Gin__, __Uber Zap__

P.s Сервис связан с [утилитой парсинга курса валют](/parse-course/README.md)

### Репозиторий на Github:  
[__postback-service__](https://github.com/developer-bwm/postback-service)  

