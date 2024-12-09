Створення простого застосунку на Meteor.js

1. Виконайте команду для встановлення Meteor:
```Bash
npm install -g meteor
```
 -g - глобальне встановлення.

2. Ініціалізація проекту:
Створити нову директорію для проекту:
```Bash
mkdir my-meteor-app
cd my-meteor-app
```

Ініціалізувати проект Meteor:
```Bash
meteor create .
```

3. Редагування файлу imports/ui/body.js:
```JavaScript
import { Meteor } from 'meteor/meteor';
import { Template } from 'meteor/templating';
import './body.html';

Template.body.helpers({
  greeting: 'Hello, world!'
});
```

4. Створення файлу imports/ui/body.html:
```HTML
<template name="body">
  <h1>{{greeting}}</h1>
</template>
```

5. Запуск сервера:
```Bash
meteor
```

Пояснення коду:
- imports/ui/body.js: Цей файл містить логіку для шаблону. Метод helpers використовується для визначення даних, які будуть доступні в шаблоні.
- imports/ui/body.html: Цей файл містить шаблон, який буде рендеритися на сторінці. Ми використовуємо {{greeting}} для відображення значення з helper-а.

Як це працює:
Meteor автоматично синхронізує дані між сервером і клієнтом, що дозволяє зміни, внесені на сервері, відразу відображати на клієнті.

Структура проекту:
```text
my-meteor-app/
├── .meteor
├── imports
│   └── ui
│       ├── body.html
│       └── body.js
├── client
├── server
└── packages
```