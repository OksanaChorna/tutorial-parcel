# tutorial-parcel

Пользователям Windows, в режиме администратора. Как запусттить Powershell в режиме администратора.

npm install --global --production windows-build-tools

## Setting up Dev

### Чтобы установить с помощью NPM:

npm install parcel-bundler --save-dev

### Создайте файл package.json в папке вашего проекта, используя:

npm init -y

### Далее, добавьте следующие скрипты в package.json вашего проекта:

{
"scripts": {
"dev": "parcel <your entry file>",
"build": "parcel build <your entry file>"
}
}

### И запустить режим разработки.

npm run dev
Во вкладке браузера перейти по адресу http://localhost:1234.

## Building

Для того чтобы создать оптимизированные файлы для хостинга, необходимо выполнить следующую команду. В корне проекта появится папка build со всеми оптимизированными ресурсами.

npm run build

## Deploying / Publishing

Сборка может автоматически деплоить билд на GitHub Pages удаленного (remote) репозитория. Для этого необходимо в файле package.json отредактировать поле homepage, заменив имя пользователя и репозитория на свои.

"homepage": "https://имя*пользователя.github.io/имя*репозитория"
Также необходимо отредактировать скрипт "predeploy".

"predeploy": "npm run build -- --public-url /имя_репозитория/"
После чего в терминале выполнить следующую команду.

npm run deploy
или

## parcel-deploy-tutorial

Мастерская: деплой билда от Parcel на GitHub Pages
Редактируем скрипт build и добавляем --public-url /имя*репозитория/
Редактрируем в package.json поле "homepage": "https://ваше*имя.github.io/имя_репозитория"
Устанавливаем пакет npm install gh-pages
npm install parcel-plugin-nuke-dist --save-dev
Добавляем npm-скрипты
"deploy": "gh-pages -d dist"
"predeploy": "npm run build"

Если нет ошибок в коде и свойство homepage указано верно, запустится сборка проекта в продакшен, после чего содержимое папки build будет помещено в ветку gh-pages на удаленном (remote) репозитории. Через какое-то время живую страницу можно будет посмотреть по адресу указанному в отредактированном свойстве homepage.

Configuration
Все паршалы файлов стилей должны лежать в папке src/sass и импортироваться в src/sass/main.scss
Изображения добавляйте в папку src/images, заранее оптимизировав их. Сборщик просто копирует используемые изображения чтобы не нагружать вашу систему оптимизацией десятков картинок, так как на слабых компьютерах это повесит систему.
