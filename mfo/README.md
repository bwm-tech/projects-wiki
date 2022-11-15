# Сайты по __МФО__

[На главную](/README.md)

---

Рекламные сайты с офферами. Написаны на React.  
В папке public файле index.html реализована логика работы фейковых поисковиков (yandex/google). Их необходимо адаптировать для управления из админ панели (новой) (получаем флаги активноти (true|false) и в зависимости от них активируем эти поисковики)

На сайте отображаются карточки офферов которые содержат информацию о каждом оффере. Так же на каждую карточку генерируется ссылка для партнерки в которой содержатся следующие параметры:  
```
 subid1/aff_sub1 - cid (uuidv4)  
 subid2/aff_sub2 - gclid/yclid (кука от яндекса или гугла)  
 subid3/aff_sub3 - tid (id рекламного кабинета)  
 subid4/aff_sub4 - id сайта (берем из панели управления)  
 subid5/aff_sub5 - utm_source (yandex|google etc)  
```

> P.s сбор параметров реализован в __src/variables.js__  
>
> ---
> __subid1/aff_sub1__  - генерируем функцией uuidv4  
> __subid2/aff_sub2__  - мы получаем из cookie  
> __subid3/aff_sub3__  - константа, получаем из gtag в index.html
> __subid4/aff_sub4__  - константа id сайта из партнерки  
> __subid5/aff_sub5__  - получаем из url query - utm_source

---

### Репозитории на Github:  
[__react-site-template__](https://github.com/bwm-tech/react-site-template) 