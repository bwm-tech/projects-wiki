# Проекты в __BWM Tech__
Описание структуры и стэка продуктов подразделения BWM Tech  

Основная часть приложений проксирована на NGINX. На данный момент у нас два сервера:
1. bwm-server.com
2. bwm-eqwrng.ru

На которых разные версии nginx. В связи с этим расположения конфигураций отличается  
На __bwm-server.com__ файл конфигурации расположен по маршруту __/etc/nginx/sites-available/__  
А на __bwm-eqwrng.ru__ в __/etc/nging/conf.d/__

## А теперь к продуктам.
Ниже представлен список продуктов разработанных в BWM Tech, список включает в себя:
1. Название продукта
2. Статус продукта на момент написания wiki (07.11.2022г.)
3. Ссылку(-и) на репозиторий(-ии) на GitHub  
  Все репозитории представленные ниже приватные, поэтому для доступак ним вам необходимо  
  запросить аккаунт GitHub у руководства иди предоставить доступ к конкретному репозиторию

Каждый продукт имеет один из статусов __PRE_RELEASE__, __RELEASE__, __SUPPORT__.  
Все статусы присвоены проектам по их __состоянию на момент написания wiki.__

1. __PRE-RELEASE__ - Приложение, сервис или утилита готовятся к релизу. Возможно наличие мелких багов.
2. __RELEASE__ - Приложение, сервис или утилита выпущеные в продакшн не более 2х недель назад.
3. __SUPPORT__ - Приложение, сервис или утилита разработаны более 3х недель назад и находятся на поддержке.

# Список продуктов

## __1. Admin Panel__
status: __PRE-RELEASE__  
repository:
[__backend__](https://github.com/bwm-tech/admin_backend)
[__frontend__](https://github.com/bwm-tech/admin_frontend)  
[Описание проекта](adminpanel/README.md)

---
## __2. Postback Service__
status: __SUPPORT__  
repository: [__открыть__](https://github.com/bwm-tech/postback_service)  
[Описание проекта](postback-service/README.md)

---
## __3. Payment Service__
status: __RELEASE__  
repository:
[__main__](https://github.com/bwm-tech/payment-service-main)
[__cron__](https://github.com/bwm-tech/payment-service-cron)  
[Описание проекта](payment-service/README.md)

---
## __4. Сайты по МФО__
status: __SUPPORT__  
repository: [__открыть__](https://github.com/bwm-tech/react-site-template)  
[__Подробнее__](mfo/README.md)

---
## __5. Утилита парсинга курса валют__
status: __SUPPORT__  
repository: [__открыть__](https://github.com/bwm-tech/parse-course)  
[__Подробнее__](parse-course/README.md)

---
## __6. Webhook Dubai__
status: __RELEASE__  
repository: [__открыть__](https://github.com/bwm-tech/webhook)  
[__Подробнее__](webhook/README.md)

---
## __7. Dubai Writer to Google Sheets__
status: __SUPPORT__  
repository: [__открыть__](https://github.com/bwm-tech/dubai-writer)  
[__Подробнее__](dubai-writer/README.md)

---
## __8. Finlab Writer to Google Sheets__
status: __SUPPORT__  
repository: [__открыть__](https://github.com/bwm-tech/finlab)  
[__Подробнее__](finlab/README.md)

---
## __9. BWM Clients Writer to Google Sheets__
status: __SUPPORT__  
repository: [__открыть__](https://github.com/bwm-tech/bwm-clients)  
[__Подробнее__](bwm-clients/README.md)

---
## __10. Analytics Service__
status: __SUPPORT__  
repository: [__открыть__](https://github.com/bwm-tech/analytics-uploader)  
Подробнее: [__Подробнее__](analytics-sender/README.md)