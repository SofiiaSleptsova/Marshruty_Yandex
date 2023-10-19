
Яндекс.Маршруты - это онлайн-сервис от компании Яндекс, предоставляющий пользователям возможность быстро и удобно планировать путешествия и маршруты. Сервис предлагает подробную информацию о дорожной ситуации, различные варианты маршрутов для пешеходов, велосипедистов и водителей, а также прокладывает оптимальные маршруты с учетом текущего движения, пробок и других факторов. 

## Содержание
- [Инструменты](#иструменты)
- [Планирование тестирования](#планированиетестирования)
- [Тестовая документация](#тестоваядокументация)
- [Deploy и CI/CD](#deploy-и-ci/cd)
- [Contributing](#contributing)
- [To do](#to-do)
- [Команда проекта](#команда-проекта)

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
