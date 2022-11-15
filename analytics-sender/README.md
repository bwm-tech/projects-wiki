# Утилита для выгрузки данных с CSV-файла в Аналитику

[На главную](/README.md)

---

Утилита с веб-интерфесом, была разработана для выгрузки данных из __CSV__ файла с конверсиями в аналитику (__yandex__/__goolge__)

Эксперементальным путем выяснилось, что в __CSV__ файле,  
Колонки subid1-subid6 могут формироваться в рандомном порядке, и не в полном составе.  
(файл аналогичен тому что в ([__Postback Service__](/postback-service/README.md))

В утилиту необходимо добавить обработчик для получения корректного номера колонок

---
Стэк: __Node.js__, __Javascript__, __Tailwind__, __EJS__, __Express.js__

### Репозитории на Github:  
[__analytics-uploader__](https://github.com/bwm-tech/analytics-uploader)

### Дополнительная информация:
[__Yandex Metrika Docs__](https://yandex.ru/dev/metrika/doc/api2/concept/about.html)