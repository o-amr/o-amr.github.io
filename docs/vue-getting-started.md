# Начало работы с Vue.js

Если вы ещё не установили Node.js или Yarn, то посетите страницу [Приступаем к работе](getting-started.md)

## Установка Vue CLI

При разработке приложений на Vue.js удобно использовать утилиту командой строки [Vue CLI](https://cli.vuejs.org/ru/).
Установка производится следующим образом:
```shell
$ yarn global add @vue/cli
# проверяем установку
$ vue -V
@vue/cli 4.5.6
```
Установка Vue CLI производится единожды для конкретной машины.

## Особенности работы в VS Code и WebStorm

VS Code не имеет встроенной поддержки Vue.js, поэтому для подсветки синтаксиса, форматирования и автодополнения кода 
требуется установить плагин [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur).

WebStorm имеет встроенную поддержку Vue.js, поэтому никаких дополнительных действий не требуется.

## Создание нового проекта

### С помощью шаблона

Выполните следующую команду, находясь в каталоге, в котором предполагается хранить проекты:
```shell
$ vue create --preset o-amr/preset-vue project-name
```
Данный шаблон содержит:
- [Vue2](https://ru.vuejs.org/index.html)
- [Vue Router](https://router.vuejs.org/ru/)
- [Vuex](https://vuex.vuejs.org/ru/)
- [Babel](https://babeljs.io/)
- [TypeScript](https://www.typescriptlang.org/) 
- [ESLint](https://eslint.org/) c конфигурацией Airbnb
- [Dart Sass](https://sass-lang.com/dart-sass)
- [Vuetify](https://vuetifyjs.com/en/)
- Шрифт [Roboto](https://fonts.google.com/specimen/Roboto)
- Иконки [MDI](https://materialdesignicons.com/)

Babel, TypeScript, ESLint добавлены с помощью плагинов Vue CLI. Информацию о конфигурации плагинов можно найти
в документации по [Vue CLI](https://cli.vuejs.org/ru/core-plugins/).

### Вручную

Переходим в каталог, в котором хранятся проекты, и инициализируем новый проект с помощью командной строки:
```shell
$ vue create project-name
```
WebStorm позволяет запустить инициализацию проекта, не используя командную строку. Выберите `File ➔ New ➔ Project...`, 
затем в появившемся диалоговом окне выберите `Vue.js`, снимите галочку `Use the default project setup (babel, eslint)` и
нажмите кнопку `Create`.

После этого запустится Vue CLI, который в виде опросника позволит сконфигурировать проект.

Выбираем с помощью стрелок `Manually select features`:
```sh
Vue CLI v4.5.12
? Please pick a preset:
  Default ([Vue 2] babel, eslint)
  Default (Vue 3 Preview) ([Vue 3] babel, eslint)
> Manually select features
```
С помощью пробела отмечаем необходимые возможности. Всё, что отмечено в данном примере, обязательно к установке:
```sh
Vue CLI v4.5.12
? Please pick a preset: Manually select features
? Check the features needed for your project:
  (*) Choose Vue version
  (*) Babel
  (*) TypeScript
  ( ) Progressive Web App (PWA) Support
  (*) Router
  (*) Vuex
  (*) CSS Pre-processors
  (*) Linter / Formatter
  ( ) Unit Testing
  ( ) E2E Testing
```
Выбираем версию `2.x`:
```sh
Vue CLI v4.5.12
? Please pick a preset: Manually select features
? Check the features needed for your project: Choose Vue version, Babel, TS, Router, Vuex, CSS Pre-processors, Linter
? Choose a version of Vue.js that you want to start the project with (Use arrow keys)
> 2.x
  3.x (Preview)
```
Отказываемся от использования `class-style` синтаксиса:
```sh
Vue CLI v4.5.12
? Please pick a preset: Manually select features
? Check the features needed for your project: Choose Vue version, Babel, TS, Router, Vuex, CSS Pre-processors, Linter
? Choose a version of Vue.js that you want to start the project with 2.x
? Use class-style component syntax? (Y/n) n
```
Cоглашаемся использовать Babel для TypeScript:
```sh
Vue CLI v4.5.12
? Please pick a preset: Manually select features
? Check the features needed for your project: Choose Vue version, Babel, TS, Router, Vuex, CSS Pre-processors, Linter
? Choose a version of Vue.js that you want to start the project with 2.x
? Use class-style component syntax? No
? Use Babel alongside TypeScript (required for modern mode, auto-detected polyfills, transpiling JSX)? (Y/n) y
```
Используем `history mode` для `Router`, это убрать символ # из адреса:
```sh
Vue CLI v4.5.12
? Please pick a preset: Manually select features
? Check the features needed for your project: Choose Vue version, Babel, TS, Router, Vuex, CSS Pre-processors, Linter
? Choose a version of Vue.js that you want to start the project with 2.x
? Use class-style component syntax? No
? Use Babel alongside TypeScript (required for modern mode, auto-detected polyfills, transpiling JSX)? Yes
? Use history mode for router? (Requires proper server setup for index fallback in production) (Y/n) y
```
Выбираем `Sass/SCSS (with dart-sass)`:
```sh
Vue CLI v4.5.12
? Please pick a preset: Manually select features
? Check the features needed for your project: Choose Vue version, Babel, TS, Router, Vuex, CSS Pre-processors, Linter
? Choose a version of Vue.js that you want to start the project with 2.x
? Use class-style component syntax? No
? Use Babel alongside TypeScript (required for modern mode, auto-detected polyfills, transpiling JSX)? Yes
? Use history mode for router? (Requires proper server setup for index fallback in production) Yes
? Pick a CSS pre-processor (PostCSS, Autoprefixer and CSS Modules are supported by default): (Use arrow keys)
> Sass/SCSS (with dart-sass)
  Sass/SCSS (with node-sass)
  Less
  Stylus
```
Выбираем `ESLint + Airbnb config`:
```sh
Vue CLI v4.5.12
? Please pick a preset: Manually select features
? Check the features needed for your project: Choose Vue version, Babel, TS, Router, Vuex, CSS Pre-processors, Linter
? Choose a version of Vue.js that you want to start the project with 2.x
? Use class-style component syntax? No
? Use Babel alongside TypeScript (required for modern mode, auto-detected polyfills, transpiling JSX)? Yes
? Use history mode for router? (Requires proper server setup for index fallback in production) Yes
? Pick a CSS pre-processor (PostCSS, Autoprefixer and CSS Modules are supported by default): Sass/SCSS (with dart-sass)
? Pick a linter / formatter config:
ESLint with error prevention only
> ESLint + Airbnb config
  ESLint + Standard config
  ESLint + Prettier
  TSLint (deprecated)
```
С помощью пробела отмечаем все опции:
```sh
Vue CLI v4.5.12
? Please pick a preset: Manually select features
? Check the features needed for your project: Choose Vue version, Babel, TS, Router, Vuex, CSS Pre-processors, Linter
? Choose a version of Vue.js that you want to start the project with 2.x
? Use class-style component syntax? No
? Use Babel alongside TypeScript (required for modern mode, auto-detected polyfills, transpiling JSX)? Yes
? Use history mode for router? (Requires proper server setup for index fallback in production) Yes
? Pick a CSS pre-processor (PostCSS, Autoprefixer and CSS Modules are supported by default): Sass/SCSS (with dart-sass)
? Pick a linter / formatter config: Airbnb
? Pick additional lint features:
  (*) Lint on save
  (*) Lint and fix on commit
```
Выбираем хранение конфигов в отдельных файлах:
```sh
Vue CLI v4.5.12
? Please pick a preset: Manually select features
? Check the features needed for your project: Choose Vue version, Babel, TS, Router, Vuex, CSS Pre-processors, Linter
? Choose a version of Vue.js that you want to start the project with 2.x
? Use class-style component syntax? No
? Use Babel alongside TypeScript (required for modern mode, auto-detected polyfills, transpiling JSX)? Yes
? Use history mode for router? (Requires proper server setup for index fallback in production) Yes
? Pick a CSS pre-processor (PostCSS, Autoprefixer and CSS Modules are supported by default): Sass/SCSS (with dart-sass)
? Pick a linter / formatter config: Airbnb
? Pick additional lint features: Lint on save, Lint and fix on commit
? Where do you prefer placing config for Babel, ESLint, etc.? (Use arrow keys)
> In dedicated config files
  In package.json
```
Не сохраняем текущую настройку в качестве шаблона:
```sh
Vue CLI v4.5.12
? Please pick a preset: Manually select features
? Check the features needed for your project: Choose Vue version, Babel, TS, Router, Vuex, CSS Pre-processors, Linter
? Choose a version of Vue.js that you want to start the project with 2.x
? Use class-style component syntax? No
? Use Babel alongside TypeScript (required for modern mode, auto-detected polyfills, transpiling JSX)? Yes
? Use history mode for router? (Requires proper server setup for index fallback in production) Yes
? Pick a CSS pre-processor (PostCSS, Autoprefixer and CSS Modules are supported by default): Sass/SCSS (with dart-sass)
? Pick a linter / formatter config: Airbnb
? Pick additional lint features: Lint on save, Lint and fix on commit
? Where do you prefer placing config for Babel, ESLint, etc.? In dedicated config files
? Save this as a preset for future projects? (y/N) n
```
После того, как будут загружены все необходимые зависимости, можно запустить проект:
```shell
# переходим в папку проекта
$ cd project-name
# запускаем сервер для разработки
$ yarn serve
```
После этого по адресу http://localhost:8080/ будет доступен текущий проект. 
Если порт 8080 занят, то будет выбран следующий свободный порт.

Собрать проект можно с помощью следующей команды:
```shell
$ yarn build
```
После этого собранный проект можно найти в каталоге `dist`.

Если проект был клонирован из репозитория или список зависимостей изменялся другим разработчиком, 
то перед запуском или сборкой необходимо установить/обновить зависимости в каталоге проекта:
```shell
$ yarn install
```

