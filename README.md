# Google HTML Styleguide RU
_Оригинальную статью можно найти [здесь](https://google.github.io/styleguide/htmlcssguide.html#HTML)._

## Навигация:
1. [Основные правила](#Основные-правила)
    - [Тип документа](#Тип-документа)
    - [Валидность](#Валидность)
    - [Семантика](#Семантика)
    - [Альтернатива для медиа](#Альтернатива-для-медиа)
    - [Разделение ответственности](#Разделение-ответственности)
    - [Ссылки на объекты](#Ссылки-на-объекты)
    - [Атрибут `type`](#Атрибут-type)

2. [Форматирование](#Форматирование)
    - [Общее форматирование](#Общее-форматирование)
    - [Перенос строк](#Перенос-строк)
    - [Кавычки](#Кавычки)

## Основные правила

### Тип документа

Используйте **HTML5**. Этот синтаксис является предпочтительным.  
Документ должен начинаться с тэга `<!DOCTYPE html>`.

Рекомендуется в атрибуте `content` тэга `<meta>`, указывать тип документа как `text/html`. Не стоит использовать XHTML, так как браузеры оптимизируют его хуже HTML.

Соотвественно, используя `text/html`, одиночные тэги нельзя закрывать. Например: `<br>`, а не `<br />`.

### Валидность

Используйте валидный HTML, насколько это возможно.

Для проверки HTML, можно использовать: [W3C HTML валидатор](https://validator.w3.org/nu/).

**Плохо:**
```html
<!-- Not recommended -->
<title>Тест</title>
<article>Это всего-лишь тест
```

**Хорошо:**
```html
<!DOCTYPE html>
<meta charset="utf-8">
<title>Тест</title>
<article>Это всего-лишь тест</article>
```

### Семантика

Элементы должны использоваться в соответствии со своим назначением. Например, `<p>` должен использоваться только для абзацев, а `<a>` только для ссылок и якорей, и т.д.

Плохо:
```html
<div onclick="goToRecommendations();">All recommendations</div>
```

Хорошо:
```html
<a href="recommendations/">All recommendations</a>
```

### Альтернатива для медиа

Медиафайлы по возможности должны иметь альтернативный контент.

Например, для `<img>` альтернативой будет являться атрибут `title`, для `<video>` это транскрипция или титры, и т.д.

Эти правила помогут в случаях, когда основной контент не удалось загрузить или пользователь имеет ограниченные возможности.

**Плохо:**
```html
<img src="spreadsheet.png">
```
**Хорошо:**
```html
<img src="spreadsheet.png" alt="Скриншот таблицы.">
```

### Разделение ответственности

Сохраняйте строгую структуру документа - разметка(HTML), стили(CSS) и скрипты(JS) должны быть разделены.

Убедитесь в том, что документ HTML, содержит только HTML и ничего более. 

Файлы HTML всегда "дороже" править, чем CSS- и JS-файлы.

**Плохо:**
```html
<title>HTML отстой</title>
<link rel="stylesheet" href="base.css" media="screen">
<link rel="stylesheet" href="grid.css" media="screen">
<link rel="stylesheet" href="print.css" media="print">
<h1 style="font-size: 1em;">HTML отстой</h1>
<p>Я читал об этом на многих сайтах и теперь я уверен:
  <u>HTML это тупость!!1</u>
<center>Я не могу поверить, что нет возможности контролировать HTML-стили не написав их заново!</center>
```

**Хорошо:**
```html
<!DOCTYPE html>
<title>My first CSS-only redesign</title>
<link rel="stylesheet" href="default.css">
<h1>My first CSS-only redesign</h1>
<p>Я читал об этом на нескольких сайтах, но сегодня я окончательно понял: разделяя ответственность, HTML моего сайта выглядит более очевидным.
<p>Это замечательно!</p>
```

### Ссылки на объекты

Не используйте ссылки на объекты, такие как `&mdash;`, `&rdquo;`, или `&#x263a`;. Не стоит надеяться на то, что одна и та же кодировка UTF-8 будет использована для файлов и редакторов, а также для команд.

Единственные исключения применяются, к символам со специальным значением в HTML (например, < и &), а также к элементам управления или "невидимым" символам (например, неразрывный пробел).

**Плохо:**
```html
Символ валюты евро - &ldquo;&eur;&rdquo;.
```

**Хорошо:**
```html
Символ валюты евро - “€”.
```

### Атрибут `type`

Для стилей и скриптов опустите атрибут `type`.

Не используйте атрибут `type` для таблиц стилей (если содержимое - CSS) и скриптов (если содержимое - JavaScript).

Этот атрибут по-умолчанию определен в браузере - `text/css` для стилей и `text/javascript` для скриптов.

**Плохо:**
```html
<link rel="stylesheet" href="https://www.google.com/css/maia.css"
  type="text/css">
<script src="https://www.google.com/js/gweb/analytics/autotrack.js"
  type="text/javascript"></script>
```

**Хорошо:**
```html
<link rel="stylesheet" href="https://www.google.com/css/maia.css">
<script src="https://www.google.com/js/gweb/analytics/autotrack.js"></script>
```

## Форматирование

### Общее форматирование

Используйте новую строку для каждого блока, списка или элемента таблицы и отступ для каждого такого дочернего элемента.

Независимо от определенных стилей (напр. изменение свойства `display`), каждый блок, список или элемент таблицы обязательно должен находится на новой строке.

Кроме того, для дочерних блоков, списков или элементов таблицы добавляйте отступы.

**Примеры:**

```html
<blockquote>
  <p><em>Space</em>, the final frontier.</p>
</blockquote>
``` 

```html
<ul>
  <li>Moe
  <li>Larry
  <li>Curly
</ul>
``` 

```html
<table>
  <thead>
    <tr>
      <th scope="col">Income
      <th scope="col">Taxes
  <tbody>
    <tr>
      <td>$ 5.00
      <td>$ 4.50
</table>
``` 

### Перенос строк

Разрывайте длинные строки и делайте перенос на новую строку.(опционально)

При переносе строк отступ новой строки должен быть равен 4. (continuation indent)

Это делает код более читабельным.

**Варианты переноса:**
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

### Кавычки

Всегда используйте двойные кавычки (`" "`) в объявлении атрибутов:

**Плохо:**
```html
<a class='maia-button maia-button-secondary'>Sign in</a>
```

**Хорошо:**
```html
<a class="maia-button maia-button-secondary">Sign in</a>
```





