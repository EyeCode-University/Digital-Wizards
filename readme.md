# 🎯 Задание: Создание REST API и React-приложения

**Task ID:** `a3f9d4c2-1`  
**Student ID:** #FD-______-___

---

## 📋 Название задания

**Разработка React-приложения с интеграцией MockAPI**

---

## 📖 Предисловие

В этом задании вы научитесь работать с REST API, создавать собственные эндпоинты на платформе MockAPI и интегрировать их в React-приложение с использованием хука `useEffect`. Это фундаментальные навыки современной веб-разработки, которые используются в реальных проектах.

---

## 🎯 Условие задания

### 1. Выбор тематики проекта

Выберите **одну** из следующих тем для вашего проекта:

- ☕ **Кофе** — каталог кофейных напитков, кофеен или сортов кофе
- 🖥️ **Серверы и инфраструктура** — мониторинг серверов, статусы систем
- 🎮 **Игры и гейминг** — библиотека игр, рейтинги, персонажи
- 👕 **Одежда** — каталог товаров, коллекции одежды

### 2. Создание MockAPI

Перейдите на [mockapi.io](https://mockapi.io/) и создайте:

- Новый проект
- Ресурс (endpoint) с минимум **5 полями**
- Добавьте минимум **8-10 записей** с реальными данными

### 3. Разработка React-приложения

Создайте React-приложение, которое:

- Использует `useEffect` для получения данных из вашего MockAPI
- Отображает полученные данные в виде карточек или списка
- Имеет адаптивный дизайн (mobile-friendly)
- Включает индикатор загрузки (loader)
- Обрабатывает ошибки при запросе

---

## 🔑 Ключевые требования

### Структура данных MockAPI

Ваш endpoint должен содержать минимум **5 полей**. Примеры:

**Для темы "Кофе":**
```json
{
  "id": "1",
  "name": "Капучино",
  "description": "Эспрессо с молочной пеной",
  "price": 250,
  "imageUrl": "https://example.com/cappuccino.jpg",
  "category": "Горячие напитки"
}
```

**Для темы "Игры":**
```json
{
  "id": "1",
  "title": "The Last of Us Part II",
  "genre": "Action-Adventure",
  "rating": 9.5,
  "imageUrl": "https://example.com/tlou2.jpg",
  "releaseYear": 2020
}
```

### React компонент с useEffect

```jsx
import { useState, useEffect } from 'react';

function App() {
  const [data, setData] = useState([]);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    const fetchData = async () => {
      try {
        const response = await fetch('YOUR_MOCKAPI_URL');
        if (!response.ok) throw new Error('Network error');
        const result = await response.json();
        setData(result);
      } catch (err) {
        setError(err.message);
      } finally {
        setLoading(false);
      }
    };

    fetchData();
  }, []);

  if (loading) return <div className="loader">Загрузка...</div>;
  if (error) return <div className="error">Ошибка: {error}</div>;

  return (
    <div className="app">
      {data.map(item => (
        <div key={item.id} className="card">
          {/* Ваша разметка карточки */}
        </div>
      ))}
    </div>
  );
}
```

### Обязательные элементы UI

1. **Loader** — анимация загрузки данных
2. **Error handling** — сообщение об ошибке
3. **Карточки/Список** — визуализация данных
4. **Адаптивность** — корректное отображение на мобильных устройствах

---

## ✅ Результат

После выполнения задания у вас должно быть:

1. ✅ Рабочий проект на MockAPI с минимум 8-10 записями
2. ✅ React-приложение с функциональным получением данных
3. ✅ Корректная обработка состояний: loading, error, success
4. ✅ Адаптивный дизайн интерфейса
5. ✅ Чистый и понятный код

### Структура проекта:
```
project/
├── src/
│   ├── App.jsx
│   ├── App.css
│   ├── components/
│   │   ├── Card.jsx
│   │   └── Loader.jsx
│   └── index.js
├── package.json
└── README.md
```

### В README.md укажите:
- Тему проекта
- Ссылку на ваш MockAPI endpoint
- Инструкцию по запуску проекта
- Скриншот работающего приложения

---

## 📤 Сдача

Загрузите ваш проект одним из способов:

- **GitHub:** Создайте репозиторий и отправьте ссылку
- **ZIP-архив:** Упакуйте проект (без `node_modules`) и загрузите

**⏳ Дедлайн:** 14 дней с момента получения задания

---

<div align="center">

**Удачи в выполнении! 🚀**

[www.eyecodeuniversity.ru](https://www.eyecodeuniversity.ru)

</div>


<ul>
    <li>Student ID: #FD-240501-006 — Данил Родионов </li>
    <li>Student ID: #FD-240501-005 — Михаил Родионов</li>
</ul>



<img src="./team-icon.jpg" alt="" />
