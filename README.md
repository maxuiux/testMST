# :zap: gulpforge - Удобный сборщик WebPack + Gulp + "FSD"(Components) :white_check_mark: 

> [!NOTE]
> Этот проект основан на [gulp-scss-starter](https://github.com/andrewalexeich/gulp-scss-starter), который является производной работой от [gulp-boiler](https://github.com/Lbdevaa/gulp-boiler), Оба проекта распространяются под лицензией GPL-3.0.

## О сборке

* Удобная структура "FSD"(Components)
* Используется препроцессор [SCSS](https://sass-lang.com/)
* Используется транспайлер [Babel](https://babeljs.io/) для поддержки современного JavaScript (ES6) в браузерах
* Используется [Webpack](https://webpack.js.org/) для сборки JavaScript-модулей
* Используется жёсткий кодгайд
* Используется проверка кода на ошибки перед коммитом

## Установка

<details>
  <summary>Если впервые устанавливайте :floppy_disk: </summary>

  Установить глобально: 
    
  * [Yarn](https://yarnpkg.com/getting-started):
    ```
    npm i -g yarn
    ```
  * [Gulp](https://gulpjs.com/):
    ```
    npm i -g gulp
    ```
  * [Bem Tools](https://www.npmjs.com/package/bem-tools-core):
    ```
    npm i -g bem-tools-core
    ```

</details>

:one: **Установить версию yarn - создаст файл .yarn\releases\yarn-x.x.x.cjs и опишет в .yarnrc.yml**
```
yarn set version berry
``` 
:two: **Скачать зависимости:**
```
yarn
```
:three: **Запустить сборку в режиме разработки:**
```
yarn run dev
```
## Команды

**Запуск сервера для разработки проекта**
```
yarn run dev
```
**Собрать проект с оптимизацией без запуска сервера**
```
yarn run build
```
**Собрать HTML-файлы**
```
yarn run build:views
```
**Скомпилировать SCSS-файлы**
```
yarn run build:styles
```
**Собрать JS-файлы**
```
yarn run build:scripts
```

## Структура проекта

```
gulpforge                                   # Ваш проект
├── dist                                    # Папка, из которой запускается локальный сервер для разработки -
│                                               при запуске yarn run dev
├── gulp-tasks                              # Папка с Gulp-тасками
├── src                                     # Папка с исходными файлами для разработки проекта
│   ├── fonts                               # Папка с файлами вашего шрифта
│   ├── img                                 # Папка с изображениями (jpg,jpeg,png,gif,tiff,svg,ico,webp,avif)
│        ├── sprites                        # Папка со всеми спрайтами (svg)
│            ├── icon                       # Папка для спрайтов иконок (svg)
│            ├── vector                     # Папка для спрайтов любых векторых изобжаний (svg)
│   ├── js                                  # Папка со всеми JS-файлами и делением на папки FSD + Components
│       ├── app                             # Папка с основными настройками проекта JS [опционально]
│       ├── components                      # Папка с произвольными блоками JS [опционально]
│       ├── entities                        # Папка с бизнес сущностями (пример: пользователь, пост, новости,
│                                               товары, группы, друзья и т.д.) [опционально]
│       ├── features                        # Папка действия пользователя (пример: лайкнуть, запостить,
│                                               прокомментировать, подписаться и т.д.) [опционально]
│       ├── libs                            # Работа с плагинами, подключение блоков, но не самих плагинов.
│            ├── swiper                     # Папка с названием плагина
│                ├── header-slider.js       # Слайдер для блока header-slider [пример]
│                ├── benefits-slider.js     # Слайдер для блока benefits-slider [пример]
│                └── items-slider.js        # Шаблон слайдера items-slider, может переиспользоваться [пример]
│       ├── pages                           # Папка с настройками для конкретной страницы [опционально]
│       ├── shared                          # Папка с переиспользоваными блоками [опционально]
│       ├── widgets                         # Папка с cамодостаточными блоками (пример: пост, карточка товара, 
│                                               шапка профиля или сайта, toolbar и т.д.) [опционально]
│       └── index.js                        # Главный JS-Файл со всеми нужными импортами из папки JS. 
│                                               Этот файл компилируется в dist/js/index.min.js 
│   ├── libs                                # На данном этапе, это обычное хранение JS и CSS файлов плагинов
│                                               Прямое подключение в HTML.
│       ├── swiper   
│            ├── swiper-bundle.min.css    
│            ├── swiper-bundle.min.js                     
│   ├── styles                              # Папка со всеми SCSS стилями
│       ├── app                             # Папка основными настройками проекта SCSS
│            ├── grid                       # Папка с настройками сетки [опционально]
│            ├── libs                       # Папка с прямыми файлами библиотек [опционально]
│                 └── normalize.scss        # Файл со сбросом стилей
│            ├── main                       # Папка с самыми главными настройками проекта
│                 ├── fonts.scss            # Подключение шрифтов
│                 ├── global.scss           # Ваши собственные глобальные стили (пример: section-padding, title, 
│                                               subtitle и т.д.)
│                 ├── settings.scss         # Глобальные настройки проекта
│                 └── variables.scss        # Хранение стилей в виде переменых SCSS $color: #fff; или нативные
│                                               root: { --color: #fff; }
│            ├── mixins                     # Папка с миксинами SCSS
│                 ├── rem.scss              # Миксин который дает возможность использовать измерение rem,
│                                               (пример: указываем в круглые скобочки цифры в пикселях - rem(24) 
│                                               или точное указание rem(24px))
│                 └── responsive.scss       # Ваши настройки для адаптива
│       ├── components                      # Папка с произвольными блоками SCSS [опционально]
│       ├── entities                        # Папка с бизнес сущностями (пример: пользователь, пост, новости,
│                                               товары, группы, друзья и т.д.) [опционально]
│       ├── features                        # Папка действия пользователя (пример: лайкнуть, запостить,
│                                               прокомментировать, подписаться и т.д.) [опционально]
│       ├── libs                            # Папка где можно подифицировать стили плагинов SCSS, по аналогии с JS выше
│       ├── pages                           # Папка со стилями страниц SCSS
│       ├── shared                          # Папка с переиспользоваными блоками [опционально]
│       ├── widgets                         # Папка с cамодостаточными блоками (пример: пост, карточка товара, 
│                                               шапка профиля или сайта, toolbar и т.д.) [опционально]
│       └── index.scss                      # Главный SCSS-Файл со всеми нужными импортами из папки STYLE. 
│                                               Этот файл компилируется в dist/css/index.min.css 
│   ├── views                               # Папка со всеми HTML-файлами
│       ├── app                             # Папка с основными файлами HTML
│            ├── head.html                  # Настройки в шапке, подключения
│            ├── scripts.html               # Подключение скриптов
│       ├── components                      # Папка с произвольными блоками HTML [опционально]
│       ├── entities                        # Папка с бизнес сущностями (пример: пользователь, пост, новости,
│                                               товары, группы, друзья и т.д.) [опционально]
│       ├── features                        # Папка действия пользователя (пример: лайкнуть, запостить,
│                                               прокомментировать, подписаться и т.д.) [опционально]
│       ├── pages                           # Папка со всеми страницами, кроме главной index.html
│       ├── shared                          # Папка с переиспользоваными блоками [опционально]
│       ├── widgets                         # Папка с cамодостаточными блоками (пример: пост, карточка товара, 
│                                               шапка профиля или сайта, toolbar и т.д.) [опционально]
│       └── index.html                      # Главная страница HTML
│   └── manifest.json                       # Файл manifest.json
├── gulpfile.babel.js                       # Настройки Gulp
├── webpack.config.js                       # Настройки Webpack
├── package.json                            # Список зависимостей
├── .yarnrc.yml                             # Настройка Yarn
├── .babelrc.js                             # Настройки Babel
├── .eslintrc.json                          # Настройки ESLint
├── .stylelintrc                            # Настройки Stylelint
├── .stylelintignore                        # Запрет на отслеживание файлов Stylelint'ом
└── .gitignore                              # Запрет на отслеживание файлов Git'ом
```
* Файлы с импортами:
    * ```index.js``` — от сюда компилируеться код в dist/js/index.min.js
    * ```index.scss``` — от сюда компилируеться код в dist/js/index.min.css


## Рекомендации по использованию
### Удобная структура для разработки html, css, javascript
За основу взят подход ["FSD"](https://feature-sliced.design/ru/), но с одним условием: использовать только названия папок, и всё. Дополнительно добавлена папка **components**, что очень удобно и важно. Здесь не нужно строго придерживаться данного подхода — суть только в удобстве. Если вам нужно удалить лишние папки, удаляйте их без зазрения совести; если нужно добавить — добавляйте; если нужно переименовать — переименовывайте. Можно создавать подпапки и многое другое. Важно только удобное деление, так как это не приложение React, Vue, Angular и другие, а профессиональная верстка — от небольших лендингов до корпоративных сайтов.
#### Как можно использовать данную структуру?
:coffee: Данный подход позволяет гибко изменять и модифицировать работу со сборкой, не теряя логику и смысл, упрощая процессы вместо их усложнения. Это не ограничивает творчество, особенно если вы верстаете по макетам дизайна из **Figma** или **Pixso**. Вам не нужно изобретать костыли или придумывать, как вписать дизайн в структуру, так как она не ставит ограничений, а наоборот, помогает расширять границы и легко масштабировать проект.

* Работа с **HTML-блоками.** Блоки можно делать независимыми и переиспользуемыми, например, добавляя кнопку в **src/shared/buttons/button.html**, а её стили и скрипты — в соответствующие **SCSS** и **JavaScript файлы**. Если блок не подходит ни в одну из папок, например, из-за индивидуального дизайна, поместите его в папку components. Если блок часто используется и требует **множества модификаций**, создайте подкаталог внутри **src/views/components** с названием страницы из **src/views/pages**, чтобы контролировать блок конкретно для этой страницы. Это позволит переиспользовать блоки, добавляя дополнительные классы и стили в одном месте — например, для блока **.benefits** создайте **src/views/components/benefits.html**, а для блока с различными вариациями на разных страницах **(.latest-orders)** используйте структуру **src/views/components/index/latest-orders.html** и **src/views/components/portfolio/latest-orders.html.** Стили и скрипты можно хранить в одном файле, например, **src/styles/components/benefits.scss** и **src/js/components/benefits.js.**

```
├── src
│   ├── js
│       ...
│       ├── components 
│           ├── latest-orders.js            # Опционально, не обязательно. Если необходимо.
│           ├── benefits.js                 # Опционально, не обязательно. Если необходимо.
│       ...
│   ├── styles
│       ...
│       ├── components 
│           ├── latest-orders.scss          # Основные стили и модификации к ним.
│           ├── benefits.scss               # Основные стили и модификации к ним.
│       ...
│   ├── views
│       ...
│       ├── components 
│           ├── index
│               ├── latest-orders.html
│           ├── portfolio
│               ├── latest-orders.html
│           └── benefits.html
│       ...
```
* Работа с **JS** и **SCSS** гораздо проще и аналогична описанному выше подходу с HTML.
* Не забывайте, что вы можете адаптировать эту структуру под свои нужды. Я показал лишь один из подходов, а ваши возможности ограничены только фантазией и потребностями.

### Почему некоторые вещи нужно делать вручную?
* Я делал сборку на основе тех, что описаны в начале. Почти всё в них автоматизировано, что очень удобно, но для меня как специалиста с большим опытом работы в верстке и со сборками в частности, стало очевидно, что плагины, используемые в Gulp, не всегда обеспечивают необходимое качество. Например, шрифты (fonts) искажаются при компиляции, изображения (img) в форматах WebP и AVIF сжимаются с потерей качества, тогда как [squoosh](https://squoosh.app/) справляется с этим лучше. Favicons также генерируются некачественно, как и изображения. Это основные примеры, но в остальном автоматизация значительно ускоряет работу, особенно с HTML, SCSS и JS файлами. Конечно, всегда есть к чему стремиться, и, возможно, когда-нибудь я создам идеальную сборку с качественной автоматизацией :grin:
  
### Страницы проекта
* Страницы проекта находятся в папке ```src/views/pages```
    * Главная страница: ```src/views/index.html```

### Шрифты
* Шрифты загружайть в папку ```src/fonts```
    * Используйте любые удобные форматы
    * Шрифты подключаются в файл в ручную ```src/styles/app/main/fonts.scss```
    * Сконвертировать локальные шрифты можно с помощью [данного сервиса](https://onlinefontconverter.com/)

### Изображения
* Изображения загружайть в папку ```src/img```
    * Поддерживаемые форматы **jpg,jpeg,png,gif,tiff,svg,ico,webp,avif**
      
### SVG-спрайты

Можно поддерживать чистоту, заменяя значения атрибутов **fill** и **stroke** в загружаемых исходных файлах ```.svg``` на **currentColor**, чтобы управлять цветом через свойство color в **SCSS**. Также вы можете менять подходы и обращаться к **SVG** через **SCSS**.

Есть две папки для двух видов спрайтов:
  - ```src/img/sprites/icon``` - Папка для спрайтов иконок (svg)
  - ```src/img/sprites/vector``` - Папка для спрайтов любых векторых изобжаний (svg)
  
```
│   ├── img                                 # Папка с изображениями (jpg,jpeg,png,gif,tiff,svg,ico,webp,avif)
│        ├── sprites                        # Папка со всеми спрайтами (svg)
│            ├── icon                       # Папка для спрайтов иконок (svg)
│            ├── vector                     # Папка для спрайтов любых векторых изобжаний (svg)
```
* Добавление в HTML:
```html
<svg>
    <use href="img/sprites/icon.svg#github"></use>
</svg>
```
```html
<svg>
    <use href="img/sprites/vector.svg#illustration-nature"></use>
</svg>
```

* Вставка через тег img:
```html
<img src="img/sprites/vector.svg#illustration-nature" alt="">
```

### Сторонние библиотеки
* На данном этапе подключение происходит стандартным образом: создайте папку с названием плагина в ```src/libs/swiper/``` и разместите внутри необходимые файлы **JS** и **CSS** плагина. Эти файлы и папки экспортируются напрямую в ```dist/libs``` и подключаются напрямую. В будущем я планирую сделать разделение на **vendor.scss** и **vendor.js**, чтобы подключать плагины импортами из **node_modules** и получать конечные файлы **vendor.min.css** и **vendor.min.js** со всеми нужными плагинами, что будет гораздо удобнее.

## Версия yarn release на проект
```4.3.1```

## Для добавления своих пакетов
```
yarn add --dev
``` 
или 
```
yarn add -D
```

