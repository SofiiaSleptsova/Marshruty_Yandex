# <a name="up" />Проект Яндекс Маршруты

***

Яндекс.Маршруты - это онлайн-сервис от компании Яндекс, предоставляющий пользователям возможность быстро и удобно планировать путешествия и маршруты. Сервис предлагает подробную информацию о дорожной ситуации, различные варианты маршрутов для пешеходов, велосипедистов и водителей, а также прокладывает оптимальные маршруты с учетом текущего движения, пробок и других факторов. 

## Содержание
- [Инструменты](#иструменты)
- [Планирование тестирования](#планированиетестирования)
- [Тестовая документация](#тестоваядокументация)
- [Deploy и CI/CD](#deploy-и-ci/cd)
- [Contributing](#contributing)
- [To do](#to-do)
- [Команда проекта](#команда-проекта)

## Требования по проекту

<details>
<summary>Требования к сервису Яндекс Маршруты 1.0 </summary>

***

### Общее описание

Яндекс.Маршруты — сервис, который строит маршруты для транспорта разных видов. Рассчитывает время и стоимость поездки.
В этом сервисе доступны несколько режимов: «Оптимальный», «Быстрый», «Свой».
В режиме «Свой» панель видов транспорта активна, можно выбрать тип транспорта. Система построит маршрут. 
Если выбрать режим «Оптимальный» или «Быстрый», система автоматически определит вид транспорта и построит маршрут. Панель видов транспорта станет неактивна.

#### Макеты

![iScreen Shoter - Safari - 231020150119](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/997cac9c-8cd3-411a-bc75-8c2b4e434f73)

![iScreen Shoter - Safari - 231020150213](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/2ecdd524-c9ed-42d6-ad72-cda16f8f3c45)

![iScreen Shoter - Safari - 231020150252](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/7c922c18-2bf7-432c-9ae6-7aaa34ebd089)

#### Интерфейс

В интерфейсе есть поля «Время начала поездки», «Откуда», «Куда». Переключатели режимов маршрута: «Оптимальный», «Быстрый» и «Свой», а также переключатели видов транспорта: свой автомобиль, каршеринг, такси, самокат, велосипед и пешком.
Пользователь вводит время отправления. Чтобы построить маршрут, нужно ввести улицу и номер дома в поля «Откуда» и «Куда». В начале и конце адреса могут быть пробелы: они допустимы, но при снятии фокуса система удалит их.

#### Описание работы интерфейса

В стартовом состоянии поля «Время начала поездки», «Откуда» и «Куда» пустые. Режимы маршрутов «Оптимальный», «Быстрый и «Свой» не выбраны; панель переключения видов транспорта неактивна.

#### Логика работы полей «Откуда» и «Куда»

Если поля адреса заполнены корректно, на карте отображаются точки А и В. Если поле «Откуда» заполнено некорректно, точка А не отображается. Если поле «Куда» заполнено некорректно, точка В не отображается. При некорректном значении поле подсвечивается красным; появляется сообщение об ошибке.
Примеры тестовых адресов есть в таблице.

#### Режим «Оптимальный» и «Быстрый»

Если выбрать режим «Оптимальный» или «Быстрый», система автоматически назначит вид транспорта; построится маршрут; отобразится время и стоимость поездки. Выбрать транспорт в этих режимах нельзя — панель видов транспорта неактивна.

#### Режим «Свой»

Если выбрать режим «Свой», панель видов транспорта активна — можно переключать. Под каждый вид транспорта строится маршрут; рассчитывается время и стоимость поездки.
Если сменить вид транспорта или поменять значение в любом поле, маршрут перестроится; время и стоимость поездки пересчитается.

#### Ограничения

![iScreen Shoter - Safari - 231020150335](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/a179dc40-b00d-4509-a965-2089272bd58f)

#### Логика расчёта

Система получает данные о начале поездки, точке А и точке В. После этого рассчитывает продолжительность и стоимость поездки по определённому алгоритму.

![iScreen Shoter - Safari - 231020150410](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/4b6ec83c-5898-45f0-b16d-430f37629c29)

#### Алгоритм: формулы

Стоимость и время поездки зависят от скорости и длины маршрута.
Скорость зависит от времени начала поездки.
Длина маршрута – от точек А и Б на карте и построенного маршрута.
Расчёт времени поездки происходит по формуле: 
t = S/V
Расчёт стоимости поездки происходит по формуле: 
Р (итоговая) = S * P (за километр) ИЛИ t * P (за время).
Вид транспорта, скорость и стоимость
Расстояние, скорость и стоимость за минуту или километр можно получить из таблиц. Этих данных достаточно, чтобы рассчитать время и стоимость поездки для каждого вида транспорта.

![iScreen Shoter - 20231020150451157](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/75bda6ea-c8c9-4e60-ad03-b6cfff7d713c)

#### Средняя скорость автомобиля

![iScreen Shoter - Safari - 231020150514](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/01ac5fc9-f795-4059-bfff-35ff92969de6)

#### Средняя скорость такси с учётом движения по выделенным полосам

![iScreen Shoter - Safari - 231020150536](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/2e7557ec-46a4-44c7-9991-94e35cb10cb4)

#### Матрица расстояний между адресами для автомобильных дорог, в километрах

![iScreen Shoter - Safari - 231020150603](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/2653edab-62bf-4a35-9e18-4d04242776cb)

#### Матрица расстояний между адресами для пешеходов, в километрах

![iScreen Shoter - Safari - 231020150628](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/feab0b28-3db9-4280-8bba-4f03c1fe8bb9)

#### Дополнительная информация

#### Алгоритм

Чтобы рассчитать время и стоимость маршрута, тестировщикам доступны таблицы со скоростью движения разных видов транспорта в разное время суток. 
Если взять такие тестовые значения, что поездка захватит несколько временных интервалов, алгоритм выберет скорость автомобиля из того диапазона, в котором поездка началась.

![iScreen Shoter - Safari - 231020150657](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/9f8d695e-1b0b-4d71-94e0-8aa2de013b6e)

#### Фокус

На макете есть несколько полей: «Время начала поездки», «Откуда» и «Куда». Валидация полей срабатывает, если фокус уходит из поля. 
Фокус — это состояние элемента интерфейса, когда элемент активен. К нему относятся все действия пользователя. 

#### Часы

В интерфейсе есть часы. Внутри — два поля ввода: часы и минуты. Обязательно применять ноль в начале, если число однозначное. Например: 09:09.
Это значит, что длина строки — всегда два символа. Чтобы проверить, что поля работают правильно, нужно указать и корректный, и неразрешённый вариант длины.   

***

</details>

## Инструменты
<p align="left"> 
  <a href="https://docs.google.com/" target="_blank" rel="noreferrer"><img src="https://w7.pngwing.com/pngs/240/1015/png-transparent-g-suite-google-docs-google-angle-rectangle-logo.png" width="36" height="36" alt="Google Sheets" /></a>
  <a href="https://app.diagrams.net" target="_blank" rel="noreferrer"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Diagrams.net_Logo.svg/2048px-Diagrams.net_Logo.svg.png" width="36" height="36" alt="draw.io" /></a>
  <a href="https://www.figma.com/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/figma-colored.svg" width="36" height="36" alt="Figma" /></a>
  <a><img src="https://d33wubrfki0l68.cloudfront.net/38b5c953a4667366685d55db55d057c86db1fc54/a0fdc/static/acae6b24d940347661ca901ea07f47c1/chrome-dev-logo-icon.png" width="36" height="36" alt="Devtools" /></a>
  <a href="https://www.jetbrains.com/youtrack/" target="_blank" rel="noreferrer"><img src="https://upload.wikimedia.org/wikipedia/commons/9/95/YouTrack_Icon.png" width="36" height="36" alt="Youtrack" /></a>
  <a href="https://www.charlesproxy.com/" target="_blank" rel="noreferrer"><img src="https://davidwalsh.name/demo/charlesproxyicon.svg" width="36" height="36" alt="Charles" /></a>
</p> 



## Планирование тестирования

### Тест-анализ

Для обеспечения полной ясности и понимания, требования были структурированы и представлены в виде ментальной карты (mindmap) с целью визуализации, чтобы убедиться, что все требования корректно охвачены и не существует недопониманий или серых зон.

<img src="https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/f27075d3-effe-4410-861f-7ea64602ace7" width="700" height="500">

[MindMap](https://drive.google.com/file/d/113BxIc8RQGmKBALEat-KJPAvswUswN1x/view?usp=sharing)

Далее провели повторный тест-анализ, используя диаграмму связей, а также подготовили блок-схему для транспорта "такси". Важно отметить, что другие виды транспорта были рассмотрены и проанализированы другими членами нашей команды тестировщиков.

<img src="https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/3b7f2a5d-9fe2-41cb-95e1-99b4237f61f2" width="250" height="600">

### Техники-тест дизайна

На данном этапе были использованы техники тест дизайна: классы эквивалентности и граничные значения для полей ввода (откуда, куда, часы и минуты)


![КЭ часть 1](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/7e02ed73-d2fb-4490-9516-ae6123217e59)
![КЭ часть 2](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/f4019505-30b6-434c-89ce-0e25b1acb01a)


## Тестовая документация

![Тест-кейсы логика интерфейса](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/3b816342-bd34-4747-9812-60c26a0ae7bf)

![Чек лист верстки](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/65f4af86-6c5c-4d50-8ba0-0f001259bd8c)

![2  Чек-лист «Способ оплаты» и «Добавление карты»](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/0d17cf3a-8502-40aa-81f4-ae331b73d875)

![2  Тест-кейсы на кнопку «Забронировать»](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/cbdb1ef1-c1dc-4cb3-b1a7-7d79a1bb181a)

![2  Тест-кейсы на логику бронирования](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/3ddb2512-3f36-4eba-9838-306bf8443f55)

![5  Чек-лист на аэротакси](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/504f9fce-e459-41f2-b823-dd2379420c92)





## Deploy и CI/CD
Расскажите, как развернуть приложение. Как запустить пайплайны и т.д.

## Contributing
Как помочь в разработке проекта? Как отправить предложение или баг-репорт. Как отправить доработку (оформить pull request, какие стайлгайды используются). Можно вынести в отдельный файл — [Contributing.md](./CONTRIBUTING.md).

## FAQ 
Если потребители вашего кода часто задают одни и те же вопросы, добавьте ответы на них в этом разделе.

### Зачем вы разработали этот проект?
Чтобы был.

## To do
- [x] Добавить крутое README
- [ ] Всё переписать
- [ ] ...

## Команда проекта
Оставьте пользователям контакты и инструкции, как связаться с командой разработки.

- [Богдан Звягинцев](tg://resolve?domain=bzvyagintsev) — Front-End Engineer

## Источники
Если вы чем-то вдохновлялись, расскажите об этом: где брали идеи, какие туториалы смотрели, ссылки на исходники кода. 
