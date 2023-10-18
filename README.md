# Яндекс Маршруты

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

<img src="https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/f27075d3-effe-4410-861f-7ea64602ace7" width="600" height="400">

[MindMap](https://drive.google.com/file/d/113BxIc8RQGmKBALEat-KJPAvswUswN1x/view?usp=sharing)

Далее провели повторный тест-анализ, используя диаграмму связей, а также подготовили блок-схему для транспорта "такси". Важно отметить, что другие виды транспорта были рассмотрены и проанализированы другими членами нашей команды тестировщиков.

<img src="https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/3b7f2a5d-9fe2-41cb-95e1-99b4237f61f2" width="200" height="600">

### Техники-тест дизайна

На данном этапе были использованы техники тест дизайна: классы эквивалентности и граничные значения для полей ввода (откуда, куда, часы и минуты)
<table style="font-size: 10px; width: 100%;">
  <tr>
    <th>Группа проверок</th>
    <th>Название класса</th>
    <th>Границы</th>
    <th>Тестовые данные внутри класса (содержимое поля)</th>
    <th>Тестовые данные на границах (содержимое поля)</th>
    <th>Пояснение и оптимизации</th>
  </tr>
  <tr>
    <td rowspan="15"><strong>Время начала поездки. Часы</strong></td>
    <td>1-2 символа (диапазон)</td>
    <td>1, 2</td>
    <td><del>2 символа - 18</del></td>
    <td>1 символ - 9</td>
    <td><em>Оптимизация выполнена зачеркиванием</em></td>
  </tr>
  <tr>
    <td>>=3 символов (диапазон)</td>
    <td>3</td>
    <td>5 символов</td>
    <td>3 символа - 180</td>
    <td><del>2 символа - 17</del></td>
    <td>4 символа - 2213</td>
  </tr>
  <tr>
    <td>Числа &lt;= -1 (диапазон)</td>
    <td>-1</td>
    <td>-7</td>
    <td>-1</td>
    <td><del>0</del></td>
  </tr>
  <tr>
    <td>Числа от 0 до 9 (диапазон)</td>
    <td>0, 9</td>
    <td>7</td>
    <td>0</td>
    <td>9</td>
  </tr>
  <tr>
    <td>Числа от 10 до 23 (диапазон)</td>
    <td>10, 23</td>
    <td>20</td>
    <td>10</td>
    <td>23</td>
  </tr>
  <tr>
    <td>Числа >=24 (диапазон)</td>
    <td>24</td>
    <td>27</td>
    <td>24</td>
    <td><del>23</del></td>
  </tr>
  <tr>
    <td>Числа от 00 до 09 (набор)</td>
    <td></td>
    <td>06</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Строка с буквами (набор)</td>
    <td></td>
    <td>аа</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Строка со спец. символами (набор)</td>
    <td></td>
    <td>9%</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Строка с дробными значениями ,</td>
    <td></td>
    <td>7,7</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Строка с дробными значениями .</td>
    <td></td>
    <td>7.7</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Строка с дробными значениями /</td>
    <td></td>
    <td>8/7</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Строка содержащая пробел (набор)</td>
    <td></td>
    <td>9</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Поле заполнено (набор)</td>
    <td></td>
    <td>21</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Поле пустое (набор)</td>
    <td></td>
    <td>поле пустое</td>
    <td></td>
    <td></td>
  </tr>
  <!-- Продолжайте таблицу аналогично -->
</table>


| Группа проверок | Название класса | Границы | Тестовые данные внутри класса (содержимое поля)   | Тестовые данные на границах (содержимое поля)     | Пояснение и оптимизации        |
|-----------------|-----------------------------|---------|--------------------------------------------------|--------------------------------------------------|--------------------------------|
| Время начала поездки. Часы | 1-2 символа (диапазон)    | 1, 2    | 2 символа - 18                                | 1 символ - 9<br>2 символа - 12<br>0 символов - пустое поле<br>3 символа - 180<br>1 символ - 9<br>2 символа - 12 | Оптимизация выполнена зачеркиванием |
|                  | >=3 символов (диапазон)    | 3       | 5 символов<br>18030                          | 3 символа - 180<br>2 символа - 17<br>4 символа - 2213   |                                |
|                  | Числа <= -1 (диапазон)     | -1      | -7<br>-1                                      | 0<br>-2             |                                |
|                  | Числа от 0 до 9 (диапазон) | 0, 9    | 7<br>0<br>9<br>-1<br>10<br>1<br>8          |                                |                                |
|                  | Числа от 10 до 23 (диапазон) | 10, 23  | 20<br>10<br>23<br>9<br>24<br>11<br>22      |                                |                                |
|                  | Числа >=24 (диапазон)      | 24      | 27<br>24<br>23<br>25                          |                                |                                |
|                  | Числа от 00 до 09 (набор) |         | 06                                           |                                |                                |
|                  | Строка с буквами (набор)   |         | аа                                           |                                |                                |
|                  | Строка со спец. символами (набор) |   | 9%                                           |                                |                                |
|                  | Строка с дробными значениями , |      | 7,7                                          |                                |                                |
|                  | Строка с дробными значениями . |      | 7.7                                          |                                |                                |
|                  | Строка с дробными значениями / |      | 8/7                                          |                                |                                |
|                  | Строка содержащая пробел (набор) |  | 9                                           |                                |                                |
|                  | Поле заполнено (набор)     |         | 21                                           |                                |                                |
|                  | Поле пустое (набор)       |         | поле пустое                                  |                                |                                |
| Время начала поездки. Минуты | 1-2 символа (диапазон)    | 1, 2    | 2 символа - 18                                | 1 символ - 9<br>2 символа - 12<br>0 символов - пустое поле<br>3 символа - 180<br>1 символ - 9<br>2 символа - 12 | Оптимизация выполнена зачеркиванием |
|                  | >=3 символов (диапазон)    | 3       | 5 символов<br>18030                          | 3 символа - 180<br>2 символа - 17<br>4 символа - 2213   |                                |
|                  | Числа <= -1 (диапазон)     | -1      | -7<br>-1                                      | 0<br>-2             |                                |
|                  | Числа от 0 до 9 (диапазон) | 0, 9    | 7<br>0<br>9<br>-1<br>10<br>1<br>8          |                                |                                |
|                  | Числа от 10 до 59 (диапазон) | 10, 59  | 20<br>10<br>59<br>9<br>60<br>11<br>58      |                                |                                |
|                  | Числа >=60 (диапазон)      | 60      | 70<br>60<br>59<br>61                          |                                |                                |
|                  | Числа от 00 до 09 (набор) |         | 06                                           |                                |                                |
|                  | Строка с буквами (набор)   |         | аа                                           |                                |                                |
|                  | Строка со спец. символами (набор) |   | 9%                                           |                                |                                |
|                  | Строка с дробными значениями , |      | 7,7                                          |                                |                                |
|                  | Строка с дробными значениями . |      | 7.7                                          |                                |                                |
|                  | Строка с дробными значениями / |      | 8/7                                          |                                |                                |
|                  | Строка содержащая пробел (набор) |  | 9                                           |                                |                                |
|                  | Поле заполнено (набор)     |         | 56                                           |                                |                                |
|                  | Поле пустое (набор)       |         | поле пустое                                  |                                |                                |
| Откуда | 1-50 символов (диапазон)    | 1, 50    | 7 символов<br>Усачева                      | 1 символ<br>У<br>50 символов УсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачеваа<br>0 символов пустое поле<br>51 символов УсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачеваа<br>2 символа<br>Ус<br>49 символов УсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачева | Оптимизация выполнена зачеркиванием |
|                  | >=51 символов (диапазон)    | 51      | 55 символов<br>УсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачеваа                      | 51 символов УсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачевааа<br>50 символов УсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачеваа<br>52 символов УсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачеваааа                      |                                |
|                  | Строка состоящая из русских букв (набор)   |       | Усачева                                |                                |                                |
|                  | Строка содержащая цифры (набор)   |           | Усачева3                        |                                |                                |
|                  | Строка содержащая тире (набор)   |             | Фрунзенская-улица               |                                |                                |
|                  | Строка содержащая точку (набор)   |          | М.Пироговская               |                                |                                |
|                  | Строка содержащая запятую (набор)   |           | Усачева,фрунзенская           |                                |                                |
|                  | Строка содержащая пробел внутри текста (набор)   | | Хамовнический Вал       |                                |                                |
|                  | Строка содержащая пробел перед текстом (набор)   | | Хамовнический       |                                |                                |
|                  | Строка содержащая пробел после текста (набор)   | | Хамовнический       |                                |                                |
|                  | Строка с другим алфавитом (набор)   |             | Usacheva                  |                                |                                |
|                  | Строка со спецсимволами (набор)   |                | Усачева?              |                                |                                |
|                  | Поле заполнено (набор)     |                       | Усачева                    |                                |                                |
|                  | Поле пустое (набор)       |                        | Поле пустое                |                                |                                |
| Куда | 1-50 символов (диапазон)    | 1, 50    | 7 символов<br>Усачева                      | 1 символ<br>У<br>50 символов УсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачеваа<br>0 символов пустое поле<br>51 символов УсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачеваа<br>2 символа<br>Ус<br>49 символов УсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачева | Оптимизация выполнена зачеркиванием |
|                  | >=51 символов (диапазон)    | 51      | 55 символов<br>УсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачеваа                      | 51 символов УсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачевааа<br>50 символов УсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачеваа<br>52 символов УсачеваУсачеваУсачеваУсачеваУсачеваУсачеваУсачеваааа                      |                                |
|                  | Строка состоящая из русских букв (набор)   |       | Усачева                                |                                |                                |
|                  | Строка содержащая цифры (набор)   |           | Усачева3                        |                                |                                |
|                  | Строка содержащая тире (набор)   |             | Фрунзенская-улица               |                                |                                |
|                  | Строка содержащая точку (набор)   |          | М.Пироговская               |                                |                                |
|                  | Строка содержащая запятую (набор)   |           | Усачева,фрунзенская           |                                |                                |
|                  | Строка содержащая пробел внутри текста (набор)   | | Хамовнический Вал       |                                |                                |
|                  | Строка содержащая пробел перед текстом (набор)   | | Хамовнический       |                                |                                |
|                  | Строка содержащая пробел после текста (набор)   | | Хамовнический       |                                |                                |
|                  | Строка с другим алфавитом (набор)   |             | Usacheva                  |                                |                                |
|                  | Строка со спецсимволами (набор)   |                | Усачева?              |                                |                                |
|                  | Поле заполнено (набор)     |                       | Усачева                    |                                |                                |
|                  | Поле пустое (набор)       |                        | Поле пустое                |                                |                                |


## Тестовая документация
Какие инструменты тестирования использованы в проекте и как их запускать. Например:

Наш проект покрыт юнит-тестами Jest. Для их запуска выполните команду:
```sh
npm run test
```

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
