Створення простого застосунку на Adonis.js

Встановлення AdonisJS глобально:
#Bash
```Bash
npm install -g @adonisjs/cli
```

2. Створення проекту
```Bash
adonis new my-adonis-app
cd my-adonis-app
```

3. Структура проекту
Після створення проекту ви отримаєте наступну структуру:

my-adonis-app/
├── .adonisrc.json
├── app/
│   ├── Controllers/
│   ├── Models/
│   ├── Providers/
│   └── Start/
├── config/
├── database/
├── public/
├── resources/
├── start/
└── tests/

4. Створення контролера
Створимо контролер HomeController в папці app/Controllers:

```Bash
adonis make:controller Home
```

Відкриємо файл app/Controllers/Http/HomeController.ts і додамо наступний код:

```TypeScript
import { HttpContextContract } from '@ioc:Adonis/Core/HttpContext'

export default class HomeController {
  public async index({ response }: HttpContextContract) {
    return response.send('Hello from AdonisJs!')
  }
}
```
5. Налаштування маршруту
Відкриємо файл start/routes.ts і додамо маршрут:

```TypeScript
import Route from '@ioc:Adonis/Core/Route'

Route.get('/', async ({ view }) => {
  return view.render('welcome')
})
```

6. Створення виду
Створимо вид welcome.edge в папці resources/views:

```HTML
<h1>{{ message }}</h1>
```

7. Запуск сервера
```Bash
adonis serve --dev
```

Пояснення коду:
- HomeController: Це контролер, який обробляє запити. Метод index відповідає за головну сторінку.
- routes.ts: Тут визначаються маршрути. Ми створили маршрут для головної сторінки (/).
- welcome.edge: Це вид, який буде відображатися на головній сторінці. Ми передаємо в нього змінну message, значення якої встановлюється в контролері.

Тепер, якщо ви відкриєте браузер і перейдете за адресою http://127.0.0.1:3333, ви побачите повідомлення "Hello from AdonisJs!".