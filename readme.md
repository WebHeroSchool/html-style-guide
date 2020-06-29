# HTML Style guide

## 1 Общие правила

### 1.1 Общие правила оформления

#### 1.1.1 Протоколы

Всегда используйте (если это возможно) протокол HTTPS для подключения изображений и других медиа файлов, файлов таблиц стилей и скриптов.

```html
<!-- Плохо (http протокол) -->
<script src="http://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>

<!-- Плохо (протокол пропущен) -->
<script src="//ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>


<!-- Хорошо -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>
```

### 1.2. Общие правила форматирования

#### 1.2.1 Отступы

Для одного отступа используйте 2 пробела.
Не используйте для отступов символы табуляции и пробелы смешенные с символами табуляции.

```html
<!-- Плохо -->
<ul>
	<li>Item</li>
</ul>

<!-- Хорошо -->
<ul>
  <li>Item</li>
</ul>
```

#### 1.2.2 Регистр

Используйте только нижний регистр для HTML разметки.

Весь HTML код должен быть в нижнем регистре. Данное правило относиться к именам элементов HTML, их атрибутам, значениям атрибутов (кроеме text/[CDATA](https://ru.wikipedia.org/wiki/CDATA)), селекторам, параметрам, и значениям параметров

```html
<!-- Плохо -->
<A HREF="/">Home</A>

<!-- Хорошо -->
<img src="web-hero-school.jpg" alt="Web Hero School" />
```

#### 1.2.3 Конечные пробелы
Удаляйте пробелы в конце строки.
Пробелы в конце строки не нужны и они могут усложнять понимание различия между разными версиями кода

```html
<!-- Плохо -->
Чаво?_

<!-- Хорошо -->
Ничаво!
```

### 1.3 Основные мета правила
#### 1.3.1 Кодировка
Используй кодировку UTF-8 (без спецификации).

Убедитесь, что ваш редактор использует кодировку UTF-8.

Укажите кодировку в HTML  шаблонах  с помощью *< meta charset="utf-8">.*
Не указывайте кодировку в таблицах стилей, так как они предполагают UTF-8

#### 1.3.2 Комментарии
Комментируйте код по мере необходимости и где это возможно.

Используйте комментарии для объяснения кода: что он охватывает, для какой цели он служит, почему используется или предпочитается соответствующее решение?

(Комментирование является необязательным, потому что не всегда реалистично ожидать то, что код будет полностью задокументирован. Всё так же зависит от сложности проекта)

```html
<!-- Комментарий в одну строку -->
```

```html
<!--
  Это пример длинного комментария. Это пример длинного комментария.
  Это пример длинного комментария. Это пример длинного комментария.
-->
```

Длинные комментарии легче заметить, если они имеют два пробела перед началом строки.

#### 1.3.3 Пометки для дальнейших действий (ТУДУШКИ)

Помечайте задачи с помощью меток **TODO**.

Выделяйте задачи используя только ключевое слово **TODO**, а не другие распространённые форматы, такие как @@

Добавляйте свои контактные данные в формате *TODO(contact)*

Добавляйте необходимое действие к ТУДУШке после знака "двоеточие"

```html
<!-- TODO(Pavel.Tretyakov): move element to center -->
<div>My awesome block</div>
```

## 2 HTML
### 2.1 Правила оформления для HTML
#### 2.1.1 Тип документа
Используйте HTML 5

HTML5 (синтаксис HTML) предпочитается для всех HTML документов: *<!DOCTYPE html>*

Хорошо использовать HTML как *text/html*. Не используйте XHTML, как *application/xhtml+xml*, так как у браузеров нет полной поддержки таких форматов и оптимизации под тип HTML.

#### 2.1.2 Одиночные теги

Закрывайте слешем одиночные теги
```html
<!-- Плохо -->
<br>

<!-- Хорошо -->
<br />
```

#### 2.1.3 Валидный HTML
Используйте валидный HTML везде, где это возможно.

Для проверки валидности вашего HTML кода используйте online инструмент:

[Nu Html Checker](https://validator.w3.org/nu/)

Для проверки HTML-кода используйте валидатор [HTMLHint](https://htmlhint.com/).

```html
<!-- Плохо -->
<title>Test</title>
<article>This is only a test.

<!-- Хорошо -->
<!DOCTYPE html>
<meta charset="utf-8">
<title>Test</title>
<article>This is only a test.</article>
```

### 2.1.4 Семантика
Используйте HTML в соответствии с его назначением.

Используйте элементы (иногда неправильно называемые «тегами») для того, для чего они были созданы. Например, используйте элементы заголовков для заголовков, элементы **p** для абзацев, **a** элементы для ссылок и т. д.

Использование семантического кода важно для его повторного использования.
```html
<!-- Плохо -->
<div onclick="goToRecommendations();">All recommendations</div>

<!-- Хорошо -->
<a href="recommendations/">All recommendations</a>
```

#### 2.1.5 Альтернатива медиа файлам

Предоставляйте альтернативный контент медиа файлам.

Убедитесь, что для таких медиа данных как изображения, видео, анимированные объекты (холсты CANVAS) у вас предоставлен альтернатинвый контент. Что имеется ввиду: для изображений -  используйте атрибут **alt**, для видео и аудио данных используйте стенограммы и подписи, если таковые имеются.

Почему это важно.
Предоставление альтернативного содержимого важно по причинам доступности: у слепого пользователя мало подсказок, чтобы понять какое перед ним изобрежине без атрибта **alt**, а у других пользователей может не быть понимания того, что переди ними видео или аудио содержимое.

Для изображений, которые несут декоративный характер не используйте атрибут **alt**.
 
 ```html
<!-- Плохо -->
<img src="spreadsheet.png">

<!-- Хорошо -->
<img src="spreadsheet.png" alt="Spreadsheet screenshot.">
```

#### 2.1.6 Разделение обязоностей

Разделяйте разметку от стилизации и от поведения.

Строго разделяйте структуру, стилизацию, сценарии и старайтесь свести к минимуму их взаимодействе.

То есть убедитесь, что HTML шаблон, содержит только HTML разметку, который служит исключительно структурным целям. Переместите всю стилизацию в таблицы стилей, а поведение - в сценарии.

Разделение структуры от стилизации важно по причинам обслуживания кода. Менять HTML документы и шаблоны всегда сложнее, чем обновлять таблицы стилей и скрипты.

 ```html
<!-- Плохо -->
<!DOCTYPE html>
<title>HTML sucks</title>

<link rel="stylesheet" href="base.css" media="screen">
<link rel="stylesheet" href="grid.css" media="screen">
<link rel="stylesheet" href="print.css" media="print">

<h1 style="font-size: 1em;">HTML sucks</h1>
<p>I’ve read about this on a few sites but now I’m sure:
  <u>
    HTML is stupid!!1
  </u>

  <center>
    I can’t believe there’s no way to control the styling of
  my website without doing everything all over again!
  </center>

<!-- Хорошо -->
<!DOCTYPE html>
<title>My first CSS-only redesign</title>
<link rel="stylesheet" href="default.css">

<h1>My first CSS-only redesign</h1>

<p>
  I’ve read about this on a few sites but today I’m actually
  doing it: separating concerns and avoiding anything in the HTML of
  my website that is presentational.
</p>

<p>
  It’s awesome!
</p>
```

#### Ссылки на символы

Не используйте ссылки на символы.

Нет необходимости использовать ссылки на такие символы как &mdash;, &rdquo;, or &#x263a; так как используемая кодировка файла (UTF-8), так же может быть использована для передачи символов.

Исключением может составлять символы используемые для HTML разметки (например **<** **&**), которые могут стать невидимыми во время использования.

```html
<!-- Плохо -->
The currency symbol for the Euro is &ldquo;&eur;&rdquo;.

<!-- Хорошо -->
The currency symbol for the Euro is “€”.
```

#### 2.1.7 Дополнительные теги

Опускайте необязательные теги (необязательно)

Для уменьшения размера файлов и удобочитаемости, попробуйте опустить дополнительные теги. [Спецификация HTML5](https://html.spec.whatwg.org/multipage/syntax.html#syntax-tag-omission) определяет какие теги могут быть опущены.

Данный подход необходимо вынести в отдельную статью, поскольку он значительно отличается от того, чему обычно обучают веб-разработчиков.

```html
<!-- Плохо -->
<!DOCTYPE html>
<html>
  <head>
    <title>Spending money, spending bytes</title>
  </head>
  <body>
    <p>Sic.</p>
  </body>
</html>

<!-- Хорошо -->
<!DOCTYPE html>
<title>Saving money, saving bytes</title>
<p>Qed.</p>
```

#### 2.1.8 Атрибуты **type**

Опускайте атрибуты **type** для таблиц стилей и скриптов.

Не используйте атрибут для таблиц стилей (если не используете CSS) и скриптов (если не используете JavaScript)

Указание атрибута **type** необязательно так как спецификация HTML 5 подразумевает text/css для стилей и text/javascript для скриптов по-умолчанию. Это можно сделать безопасно даже для старых браузеров

```html
<!-- Плохо -->
<link rel="stylesheet" href="https://www.google.com/css/maia.css"
  type="text/css">

<!-- Хорошо -->
<link rel="stylesheet" href="https://www.google.com/css/maia.css">

<!-- Плохо -->
<script src="https://www.google.com/js/gweb/analytics/autotrack.js"
  type="text/javascript"></script>

<!-- Хорошо -->
<script src="https://www.google.com/js/gweb/analytics/autotrack.js"></script>
```

#### 2.1.9 Подключение таблицы стилей

Подключайте файлы стилей внутри элемента <head>.

Подключаемые файлы внутри элемента head, будут загружены впервую очередь, что обеспечивает большую уверенность в том, что верстка не сламается во время прогрузки контента.

```html
<!-- Хорошо -->
<html>
<head>
  <link rel="stylesheet" href="https://www.google.com/css/maia.css">
</head>
<body>
  <p>Some content</p>
</body>
</html>

<!-- Плохо -->
<html>
<head></head>
<body>
  <link rel="stylesheet" href="https://www.google.com/css/maia.css">
  <p>Some content</p>
</body>
</html>
```

#### 2.1.10 Подключение скриптов
Скрипты должны подключаться в самом низу страницы, чтобы при её загрузке не блокировать отображение содержимого.
<!-- Хорошо -->
<!DOCTYPE html>
<html lang="ru">
  <head>…</head>
  <body>
    <script src="app.js"></script>
  </body>
</html>

<!-- Плохо -->
<!DOCTYPE html>
<html lang="ru">
  <head>
    <script src="app.js"></script>
  </head>
  <body>…</body>
</html>

#### 2.1.11 Порядок атрибутов
Атрибут класса у HTML-элементов пишется первым. Единообразное написание помогает легче считывать код и быстрее разбираться в назначении блоков по их классам.

Остальные атрибуты могут быть расставлены в любом порядке, но тоже единообразно для одинаковых элементов.

```html
<!-- Хорошо -->
<a class="element element-big" id="element" href="/" data-name="element">Ссылка</a>

<input class="form-control" type="text" name="test">

<img class="pets-picture" src="cats.jpg" alt="Изображение котиков">
```

#### 2.1.12 Логические атрибуты

Для логических атрибутов (например, checked, disabled, required) значение не указывается, а сами атрибуты указываются последними и в единообразной последовательности во всём документе.

```html
<!-- checked="checked" необязательно -->
<input type="checkbox" required checked>

<input type="text" disabled>

<select>
  <option value="1" selected>1</option>
</select>
```

#### 2.1.13 Подписи полей ввода

Связывайте элементы поля <input> с елментом <label>

Для улучшения взаимодействия пользователя с элементами форм, при нажатии на подпись поля, оно должно активироваться. Для этого элемент формы связывается с его описанием с помощью идентификатора и атрибута for тега <label>.

```html
<!-- Хорошо: элемент формы radio связан с подписью через идентификатор -->
<input type="radio" id="choose">
<label for="choose">Радио кнопка</label>

<!-- Хорошо: элемент формы radio и подпись обёрнуты в label -->
<label>
  <input type="radio"> Радио кнопка
</label>

<!-- Плохо: подпись не связана с элементом формы -->
<input type="radio" id="choose"> Радио кнопка
```

#### 2.1.14 Атрибут языка

Указываете атрибут lang в элементе <html>.

Для элемента <html> в атрибуте lang должен указываться соответствующий язык документа. Это помогает инструментам синтеза речи определить, какое использовать произношение или системам перевода, какие использовать языковые правила.

```html
<!DOCTYPE html>
<html lang="ru">
  <head>…</head>
  <body>…</body>
</html>
```

#### 2.1.15 Размеры изображений

Укаывайте размеры для изображений

Всегда определяйте ширину и высоту изображений. Это уменьшает "мерцание" верстки во время загразуки, т.к. браузер резервирует пространство для изображений во время зазгурзки.

```html
<!-- Хорошо -->
<img src="html5.gif" alt="HTML5" style="width:128px;height:128px">
````

```html
<!-- Плохо -->
<img src="html5.gif">
```

#### 2.1.16 Елемент title

Элемент \<title\> является обязательным в HTML.

Содержание заголовка страницы очень важно для поисковой оптимизации (SEO)! Заголовок страницы используется алгоритмами поисковой системы для определения порядка при отображении страниц в результатах поиска.

Элемент \<title\>:
- определяет заголовок на панели инструментов браузера
- предоставляет заголовок для страницы, когда она добавляется в избранное
- отображает заголовок страницы в результатах поиска

Постарайтесь сделать название максимально точным и значимым.

```html
<title>HTML Style Guide and Coding Conventions</title>
````

#### 2.1.17 Настройка viewport

Viewport - это видимая область на веб-странице и она зависит от устройства на котором просматривается страница. На мобильном телефоне она будет меньше, чем на экране компьютера. Следует включить элемент <meta> не все ваши страницы:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Эта инструкция говорит браузеру о том, как управлять размерами и масштабированием страницы.

Параметр width = device-width устанавливает ширину страницы, которая будет соответствовать ширине экрана устройства (которая зависит от устройства).

initial-scale = 1.0 устанавливает начальный уровень масштабирования при первой загрузке страницы браузером

Без метатега viewport

![Без метатега viewport](https://www.w3schools.com/css/img_viewport1.png)

С метатегом viewport

![С метатегом viewport](https://www.w3schools.com/css/img_viewport2.png)

#### 2.1.16 Доступ JavaScript к HTML элементам

Использование «неопрятного» HTML-кода может привести к ошибкам JavaScript.

Примеры ниже будут давать разные результаты:

```html
<div id="demo"></div>
```

```javascript
// Ошибка Cannot set property 'innerHTML' of null
getElementById("Demo").innerHTML = "Hello";

// Сработает корректно. 
getElementById("demo").innerHTML = "Hello";
```

### 2.2 Правила оформления HTML

#### 2.2.1 Общее форматирование
Используйте новую строку для каждого блока, списка или элемента таблицы и сделайте дополнительный отступ для каждого нового дочернего элемента.

```html
<blockquote>
  <p><em>Space</em>, the final frontier.</p>
</blockquote>
```

```html
<ul>
  <li>Moe<li>
  <li>Larry<li>
  <li>Curly<li>
</ul>
```

```html
<table>
  <thead>
    <tr>
      <th scope="col">Income</th>
      <th scope="col">Taxes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>$ 5.00</td>
      <td>$ 4.50</td>
    </tr>
  </tbody>
</table>
```

#### 2.2.2 Перенос HTML строк
Переносите длинные строки (опционально)

Хотя для HTML нет рекомендации по длине строк, вы можеете переносить длинные строки, если это значительно улучшает читабельность кода.

При переносе длинных строк, каждая новая пересенная строка должна иметь отсуп не менее 4-х пробелов от отступа исходной строки.

Варианты переноса.

```html
<md-progress-circular md-mode="indeterminate" class="md-accent"
    ng-show="ctrl.loading" md-diameter="35">
</md-progress-circular>
```

```html
<md-progress-circular
    md-mode="indeterminate"
    class="md-accent"
    ng-show="ctrl.loading"
    md-diameter="35">
</md-progress-circular>
```

```html
<md-progress-circular md-mode="indeterminate"
                      class="md-accent"
                      ng-show="ctrl.loading"
                      md-diameter="35">
</md-progress-circular>
```

#### 2.2.3 HTML Кавычки

##### 2.2.3.1 Использование ковычек
Всегда выделяйте в ковычки значение атрибутов

```html
<!-- Хорошо -->
<table class="striped">
```

```html
<!-- Плохо -->
<table class=table striped>
```

##### 2.2.3.2 Двойные ковычки
Значения атрибутов выделяйте в двойные ковычки (""), а не одинарные ('').

```html
<!-- Плохо -->
<a class='maia-button maia-button-secondary'>Sign in</a>
```

```html
<!-- Хорошо -->
<a class="maia-button maia-button-secondary">Sign in</a>
```

#### 2.2.4 Пробелы и знаки равенства

Интерпретаторы HTML разметки допускают пробелы вокруг равенства. Но без этих пробелов код легче читается.

```html
<!-- Хорошо -->
<link rel="stylesheet" href="styles.css">
```

```html
<!-- Плохо -->
<link rel = "stylesheet" href = "styles.css">
```

#### 2.2.5 Пустые строки

Не добавляйте пустые строки, пробелы или отступы без причины.

Для удобства чтения добавьте пустые строки для разделения больших или логических блоков кода.

```html
<!-- Хорошо -->
<body>

<h1>Famous Cities</h1>

<h2>Tokyo</h2>
<p>Tokyo is the capital of Japan, the center of the Greater Tokyo Area,
and the most populous metropolitan area in the world.
It is the seat of the Japanese government and the Imperial Palace,
and the home of the Japanese Imperial Family.</p>

</body>
```

```html
<!-- Плохо -->
<body>

  <h1>Famous Cities</h1>

  <h2>Tokyo</h2>

  <p>
    Tokyo is the capital of Japan, the center of the Greater Tokyo Area,
    and the most populous metropolitan area in the world.
    It is the seat of the Japanese government and the Imperial Palace,
    and the home of the Japanese Imperial Family.
  </p>

</body>
```

```html
<!-- Хорошо пример таблицы -->
<table>
  <tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>A</td>
    <td>Description of A</td>
  </tr>
  <tr>
    <td>B</td>
    <td>Description of B</td>
  </tr>
</table>
```

```html
<!-- Хорошо list example -->
<ul>
  <li>London</li>
  <li>Paris</li>
  <li>Tokyo</li>
</ul>
```

### 2.3. Файлы

#### 2.3.1 Регистр имён файлов

Используйте имена файлов в нижнем регистре

Некоторые веб-серверы (Apache, Unix) чувствительны к регистру имен файлов: файл с именем «london.jpg» не будет доступно при обращении по имени «London.jpg».

Другие веб-серверы (Microsoft, IIS) не чувствительны к регистру: файл с именем «london.jpg» будет так же доступен по «London.jpg».

Если вы используете сочетание прописных и строчных букв, вы должны внимательно следить за этим.

Если вы поменяете веб-сервер с того, который не учитывает регистр файлов, на тот, который учитывает, то это может сломать ваше приложение.

Чтобы избежать этих проблем, всегда используйте строчные имена файлов!

#### 2.3.2 Расширения файлов

Файлы HTML должны иметь расширение .html или .htm.
Между расширениями .htm и .html нет никакой разницы.
Оба будут рассматриваться как HTML любым веб-браузером и веб-сервером.

CSS-файлы должны иметь расширение .css.

Файлы JavaScript должны иметь расширение .js.

#### 2.3.3 Имена файлов по умолчанию
Если в конце URL-адреса не указано имя файла (например, «https://www.w3schools.com/»), сервер просто добавляет имя файла по умолчанию, например «index.html», «index.htm», « default.html "или" default.htm ".

Если ваш сервер настроен только с «index.html» в качестве имени файла по умолчанию, ваш файл должен называться «index.html», а не «default.html».

Однако серверы могут быть настроены с несколькими именами файлов по умолчанию, и обычно вы можете установить столько имен файлов по умолчанию, сколько необходимо.

## Дополнительные ссылки
[Самый первый сайт в мире](https://www.w3.org/History/19921103-hypertext/hypertext/WWW/TheProject.html)

[HTMLHint - валидация HTML](https://htmlhint.com/)

[Nu Html Checker - сервис для валидации HTML кода](https://validator.w3.org/nu/)

## Источники
https://google.github.io/styleguide/htmlcssguide.html

https://codeguide.academy/html-css.html#html-doctype

https://www.w3schools.com/html/html5_syntax.asp

https://html.spec.whatwg.org/multipage/syntax.html