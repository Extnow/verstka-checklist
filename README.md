<h2 align="center">Verstka Checklist</a></h2>

<p align="center">
  <em>Взято на основе https://frontendchecklist.io/ и адаптировано под себя</em>
</p>

## Содержание

1. **[Head](#head)**
2. **[HTML](#html)**
3. **[Web-шрифты](#web-шрифты)**
4. **[CSS](#css)**
5. **[Картинки](#Картинки)**
6. **[Доступность](#Доступность)**
7. **[Производительность](#Производительность)**

## Как этим пользоваться?

* 🟢  означает, что пункт **рекомендован**, но может быть пропущен в некоторых случаях.
* 🟡 элемент **крайне рекомендован** и может быть пропущен только в очень специфических ситуациях. Невыполнение некоторых пунктов может иметь негативные последствия, например с точки производительности или SEO.
* 🔴 такой пункт **обязателен**. Может сломать страницу или привести к проблемам с доступностью (accessibility) и SEO. Проверяйте такие элементы в первую очередь.

Некоторые комментарии снабжены иконками, чтобы вы лучше понимали, какой контент или помощь можно найти:

* 📖: документация или статья
* 🛠: он-лайн инструменты / утилиты для проверки
* 📹: медиа или видео контент

---

## Head

### Мета-теги

* [ ] **Doctype:** 🔴 Doctype относится к HTML5 и находится в самом верху HTML страниц.

```html
<!doctype html> <!-- HTML5 -->
```

> * 📖 [Определение кодировки (англ.) - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

*Следующие 3 мета-тега (Charset, X-UA Compatible and Viewport) должны быть расположены в самом начале `<head>`.*

* [ ] **Charset:** 🔴 Кодировка (UTF-8) задана правильно.

```html
<!-- Задать кодировку документа -->
<meta charset="utf-8">
```

* [ ] **X-UA-Compatible:** 🟡 Тег X-UA-Compatible присутствует.

```html
<!-- Проинструктировать Internet Explorer использовать последний движок рендеринга -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
```

> * 📖 [Задать режим совместимости Internet Explorer (англ.)](https://msdn.microsoft.com/en-us/library/jj676915(v=vs.85).aspx)

* [ ] **Viewport:** 🔴 Viewport задан правильно.

```html
<!-- Задать viewport для responsive дизайна -->
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
```

* [ ] **Title:** 🔴 Задан на всех страницах (SEO: Google рассчитывает ширину символов в title и обрезает примерно от 472 до 482 пикселей. Так что предел длины title около 55 символов).

```html
<!-- Document Title -->
<title>Название короче 55 символов</title>
```

> * 📖 [Title - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)
> * 🛠 [SERP Snippet Generator](https://www.sistrix.com/serp-snippet-generator/)

* [ ] **Description:** 🔴 Description задан, уникален и короче 150 символов.

```html
<!-- Meta Description -->
<meta name="description" content="Описание страницы короче 150 символов">
```

> * 📖 [Meta Description - HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_an_author_and_description)

* [ ] **Favicons:** 🟡 Иконки отображаются корректно. Если у вас только один `favicon.ico`, положите его в корень сайта. Обычно вам не нужно ничего добавлять в разметку. Однако, хорошей практикой считается сделать ссылку как в примере ниже. На сегодняшний день **рекомендован PNG формат** вместо `.ico`(разрешение: 32x32px).

```html
<!-- Стандартный favicon -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- Рекомендованный формат favicon -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
```

> * 🛠 [Favicon Generator](https://www.favicon-generator.org/)
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
> * 📖 [Favicon шпаргалка](https://github.com/audreyr/favicon-cheat-sheet)
> * 📖 [Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
> * 📖 [PNG favicons - caniuse](https://caniuse.com/#feat=link-icon-png)

### HTML теги

* [ ] **Атрибут lang:** 🔴 Атрибут `lang` задан в соответствии с языком страницы.

```html
<html lang="en">
```

* [ ] **Порядок CSS:** 🔴 Все CSS файлы должны загружаться перед любыми JavaScript файлами в `<head>`. (За исключением случаев, когда JS файлы загружаются асинхронно в верху страницы).

**[⬆ наверх](#Содержание)**

---

## HTML

### Лучшие практики

* [ ] **Семантические элементы HTML5:** 🔴 Семантические элементы HTML5 используются должным образом (header, section, footer, main, nav, article, aside, time...).

> * 📖 [HTML Reference](http://htmlreference.io/)

* [ ] **Страницы ошибок:** 🔴 Страницы ошибок 404 и 5xx существуют. Не забывайте, что в страницы ошибок 5xx должны быть включены их стили, чтобы обойтись без подгрузки с сервера.

* [ ] **Удаление комментариев:** 🟢 Ненужный код должен быть удалён перед отправкой в production.

### Тестирование HTML

* [ ] **W3C совместимость:** 🔴 Все страницы должны быть проверены W3C валидатором.

> * 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** 🔴 Инструменты, которые помогают анализировать проблемы в HTML.

> * 🛠 [Dirty markup](https://dirtymarkup.com/)

> * 🛠 [Sonar a linting tool for the web](https://sonarwhal.com/)

* [ ] **Проверка ссылок:** 🔴 Нет сломанных ссылок, нет ошибок 404.

> * 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

**[⬆ наверх](#Содержание)**

---

## Web-шрифты

> **Примечание:** Использование web-шрифтов может вызвать мерцание или исчезновение текста (FOUT - Flash of Unstyled Text, FOIT - Flash of Invisible Text). Так что убедитесь, что задан резервный шрифт, либо используйте загрузчик шрифтов чтобы держать ситуацию под контролем.
> * 📖 [Google Technical considerations about webfonts](https://developers.google.com/fonts/docs/technical_considerations)

* [ ] **Форматы web-шрифтов:** 🔴 WOFF и WOFF2 поддерживаются всеми браузерами.

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff)
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)
> * 📖 [Оптимизация шрифтов](http://www.nicothin.pro/page/webfonts-min)

* [ ] **Размер web-шрифтов:** 🔴 Размер шрифтов суммарно не превышает 2 MB.

**[⬆ наверх](#Содержание)**

---

## CSS

> **Примечание:** Ознакомьтесь с [CSS guidelines](https://cssguidelin.es/) и [Sass Guidelines](https://sass-guidelin.es/), которых придерживаются большинство разработчиков. Если у вас есть сомнения насчёт CSS свойств, посетите [CSS Reference](http://cssreference.io/). Кроме того взгляните на короткий гайд [Code Guide](http://codeguide.co/).

* [ ] **Отзывчивый (responsive) веб-дизайн:** 🔴 Дизайн должен быть отзывчивым.
* [ ] **Препроцессоры:** 🟢 Используйте CSS препроцессоры (например [Sass](http://sass-lang.com/), [Less](http://lesscss.org/), [Stylus](http://stylus-lang.com/)).
* [ ] **Уникальные ID:** 🔴 Если используются Id, убедитесь, что они уникальны в пределах страницы.
* [ ] **Сброс (reset) CSS:** 🔴 Используются актуальные версии инструментов для нормализации CSS (reset, normalize или reboot). *(Если используете CSS фреймворк типа Bootstrap или Foundation, Normalize уже в них включён.)*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **Вендорные префиксы:** 🔴 CSS вендорные префиксы используются и генерируются в соответствии с поддерживаемыми браузерами.

> * 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### Производительность CSS

- [ ] **Конкатенация:** 🔴 CSS файлы сконкатенированы в один файл. *(Не для HTTP/2)*.
- [ ] **Минификация:** 🔴 Все CSS файлы минифицированы.
- [ ] **Неблокирующий CSS:** 🟡 CSS файлы должны быть неблокирующими DOM, чтобы избежать потерь времени.

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
> * 📖 [Example of preload CSS using loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **Неиспользуемый CSS:** 🟢 Удалите неиспользуемые стили.

> * 🛠 [UnCSS Online](https://uncss-online.com/)
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [Chrome DevTools Coverage](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)


### Тестирование CSS

* [ ] **Stylelint:** 🔴 В CSS или SCSS файлах нет ошибок.

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **Отзывчивый web-дизайн:** 🔴 Все страницы были протестированы на следующих контрольных точках: 320px, 768px, 1024px (может быть больше а зависимости от проекта).

* [ ] **CSS валидатор:** 🟡 CSS был протестирован, ошибки исправлены.

> * 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

**[⬆ наверх](#Содержание)**

---

## Картинки

> **Примечание:** Для полного понимания оптимизации картинок прочтите бесплатную электронную книгу **[Essential Image Optimization](https://images.guide/)** от Addy Osmani.

### Лучшие практики

* [ ] **Оптимизация:** 🔴 Все картинки оптимизированы для рендеринга в браузере.

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Используйте [ImageOptim](https://imageoptim.com/) для бесплатной оптимизации картинок.
> * 🛠 Используйте [Kraken.io](https://kraken.io/web-interface) как крутую альтернативу для оптимизации png и jpg. До 1 Mb бесплатно.
> * 🛠 Используйте [TinyPNG](https://tinypng.com/) для оптимизации png, apng (анимированный png) and jpg без потери качества. Есть как платная, так и бесплатная версия.
> * 🛠 [ZorroSVG](http://quasimondo.com/ZorroSVG/) jpg-подобное сжатие для прозрачных картинок  использованием svg масок.
> * 🛠 [SVGO](https://github.com/svg/svgo) инструмент под Nodejs для оптимизации SVG файлов. 
> * 🛠 [SVGOMG](https://jakearchibald.github.io/svgomg/) web версия SVGO для онлайн оплимизации SVG файлов.

* [ ] **Picture/Srcset:** 🟡 Используйте picture/srcset чтобы задать наиболее подходящую картинку для текущего viewport.

> * 📖 [How to Build Responsive Images with srcset](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/)

* [ ] **Retina:** 🟡 Вы используете картинки большего размера 2x или 3x для поддержки дисплеев retina.
* [ ] **Спрайты:** 🟡 Мелкие картинки объединены в спрайт файл. В случае иконок это может быть SVG файл.
* [ ] **Width и Height:** 🔴 Задайте атрибуты `width` и `height` для `<img>` если размеры картинки заранее известны. Может быть пропущен для задания размеров через CSS.
* [ ] **Альтернативный текст:** 🔴 Для всех `<img>` задан альтернативный текст, который описывает картинку.

> * 📖 [Alt-texts: The Ultimate Guide](https://axesslab.com/alt-texts/)

* [ ] **Фотографии** 🟡 Добавлены и оптимизированы в формате .jpg
* [ ] **Картинки с прозрачностью и(или) текстом** 🟡 Добавлены и оптимизированы в формате .png
* [ ] **Иконки** 🟡 По возможности добавлены и оптимизированы в формате .svg

**[⬆ наверх](#Содержание)**

---

## Доступность

> **Примечание:** Ознакомьтесь с плейлистом [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

#### Заголовки

* [ ] **H1:** 🔴 На всех страницах есть H1, который отличается от title страницы.
* [ ] **Заголовки:** 🔴 Заголовки должны идти в правильном порядке (от H1 к H6).

> * 📹 [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

### Семантика

- [ ] **Специальные типы input для HTML5:** 🟡 Это особенно важно для мобильных устройств, т.к. там используется разные клавиатуры для разных типов вводимых данных.

> * 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Формы

* [ ] **Label:** 🔴 `<label>` задан для каждого элемента формы. Если его применить нельзя, используйте `aria-label`.

> * 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### Контрастность цветов

> * 📖 [Здесь можно проанализировать цвет фона и текста на соблюдение необходимой контрастности](http://colory.ru/contrastanalizer)

### Тестирование доступности

* [ ] **Проверка на соответствие стандартам:** 🔴 Используйте инструмент WAVE для проверки.

> * 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **Клавиатурная навигация:** 🔴 Пройдитесь по вашему сайту, используя только клавиатуру. Все интерактивные элементы должны быть доступны.
* [ ] **Стили для фокуса:** 🔴 Если фокус запрещён, к элементу под фокусом должны применяться специальные стили.

> * 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ наверх](#Содержание)**

---

## Производительность

* [ ] **Проверка скорости загрузки страниц:** 🔴

> * 🛠 [GooglePagespeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [SpeedTest](http://pr-cy.ru/speed_test/)

**[⬆ наверх](#Содержание)**
