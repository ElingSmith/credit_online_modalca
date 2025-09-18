## 📦 Установка

Подключите скрипт в HTML:

```html
<script src="modalca.js" 
        data-domain="example.com"
        data-style="green"
        data-type="strict"
        data-position="center"
        data-delay="3000"
        data-policy-url="/policy.html"
        data-api-url="https://api.mtk-ru.ru/api/feedback_kredit"
        data-show-timer="true"
        data-timer-duration="600"
        data-force-submit="true"></script>
````

Скрипт автоматически инициализируется при загрузке страницы.

---

## ⚙️ Параметры

| Параметр        | Тип     | Значение по умолчанию                       | Описание                                                            |
| --------------- | ------- | ------------------------------------------- | ------------------------------------------------------------------- |
| `domain`        | string  | `window.location.hostname`                  | Домен сайта для передачи в API                                      |
| `style`         | string  | `green`                                     | Цветовая схема модалки: `green`, `red`, `blue`, `dark`, `light`     |
| `type`          | string  | `strict`                                    | Тип модалки: `strict`, `urgent`, `consult`                          |
| `position`      | string  | `center`                                    | Позиция модалки: `center`, `top`, `bottom`                          |
| `delay`         | number  | `3000`                                      | Задержка появления модалки в миллисекундах                          |
| `policyUrl`     | string  | `/policy.html`                              | Ссылка на страницу политики конфиденциальности                      |
| `apiUrl`        | string  | `https://api.mtk-ru.ru/api/feedback_kredit` | URL для отправки данных формы                                       |
| `showTimer`     | boolean | `true`                                      | Показывать таймер на модалке (только для типов `urgent` и `strict`) |
| `timerDuration` | number  | `600`                                       | Продолжительность таймера в секундах                                |
| `forceSubmit`   | boolean | `true`                                      | Если `true`, модалку нельзя закрыть без отправки формы              |

---

## 🎨 Цветовые схемы

* **green** — зеленая тема
* **red** — красная тема
* **blue** — синяя тема
* **dark** — темная тема
* **light** — светлая тема

---

## 📝 Типы модалок

| Тип       | Заголовок                                           | Подзаголовок                                            | Кнопка                | Примечание                                        |
| --------- | --------------------------------------------------- | ------------------------------------------------------- | --------------------- | ------------------------------------------------- |
| `strict`  | Одобрение с просрочками и плохой кредитной историей | Предварительное одобрение за 5 минут                    | Отправить заявку      | Без скрытых комиссий • Решение в день обращения   |
| `urgent`  | Только сегодня — сниженная ставка!                  | Получите одобрение за 5 минут                           | Получить предложение  | Мы перезвоним в течение 10 минут                  |
| `consult` | Бесплатная консультация                             | Узнайте: какие документы нужны и как избежать переплаты | Получить консультацию | Наш специалист свяжется с вами в течение 10 минут |

> Для типов `urgent` и `strict` можно отображать таймер.

---

## 🛠 Примеры использования

### 1️⃣ Через HTML-атрибуты

```html
<script src="modalca.js"
        data-style="blue"
        data-type="consult"
        data-delay="2000"
        data-force-submit="false"></script>
```

### 2️⃣ Через JS

```js
const widget = new PopupWidgetClass({
    domain: 'example.com',
    style: 'red',
    type: 'urgent',
    position: 'center',
    delay: 1000,
    policyUrl: '/privacy',
    apiUrl: 'https://api.mtk-ru.ru/api/feedback_kredit',
    showTimer: true,
    timerDuration: 300,
    forceSubmit: true
});

// Управление виджетом
widget.show();  // показать модалку
widget.hide();  // скрыть модалку (если forceSubmit=false)
```

---

## ⏱ Таймер

* Отображается только при `showTimer: true` и типе модалки с таймером (`urgent` или `strict`)
* Формат: `мм:сс`
* Время истекает — таймер останавливается, модалка скрывается если `forceSubmit=false`

Пример через HTML:

```html
<script src="modalca.js"
        data-type="urgent"
        data-show-timer="true"
        data-timer-duration="300"></script>
```

---

## 📸 Фото модалок

| Strict | Urgent | Consult |
|--------|--------|---------|
| ![Strict modal](https://github.com/user-attachments/assets/b6d4db3a-c82a-4550-b663-56deb43f3826) | ![Urgent modal](https://github.com/user-attachments/assets/4b274fe9-605b-4e49-9107-567e295d03a2) | ![Consult modal](https://github.com/user-attachments/assets/578efd33-3834-4b25-a519-d39e3de897e9) |
| Одобрение с просрочками и плохой кредитной историей | Срочная акция — сниженная ставка | Бесплатная консультация |


> Замените ссылки на свои файлы в папке `images`.

---

## ✅ Особенности

* Маска для телефона: `+7 (___) ___-__-__`
* Валидация email (необязательное поле)
* Проверка имени и согласия с политикой
* Force submit — нельзя закрыть модалку без отправки
* Таймер обратного отсчета для срочных модалок
* Анимация появления и ошибок (shake)

---

## 🔗 API

**POST** на `apiUrl` с телом:

```json
{
  "name": "Иван Иванов",
  "phone": "+79001234567",
  "email": "ivan@mail.com",
  "domain": "example.com",
  "type": "strict"
}
```

> Возвращает статус `200` при успешной отправке.


