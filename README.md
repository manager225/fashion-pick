# Приложение для выбора вещей

![Vue.js](https://img.shields.io/badge/Vue.js-4FC08D?style=for-the-badge&logo=vue.js&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)

## 📋 Описание

Это интерактивное приложение для выбора вещей, разработанное на Vue.js с использованием Vite. Приложение позволяет пользователям выбирать вещи из двух списков и отображать выбранные элементы в соответствующих секциях.

## ✨ Функциональность

- **Левый нижний блок**: Отображает список вещей пользователя
- **Правый нижний блок**: Отображает список вещей на выбор
- **Левый верхний блок**: Показывает выбранные вещи пользователя (до 6 штук)
- **Правый верхний блок**: Показывает одну выбранную вещь из списка вещей на выбор

## 🔧 Механика работы

- Из левого нижнего блока можно выбрать от 1 до 6 вещей
- Из правого нижнего блока можно выбрать только 1 вещь
- Выбранные вещи отображаются в соответствующих верхних блоках
- Повторный клик по выбранной вещи отменяет выбор

## 🚀 Установка и запуск

```bash
# Установка зависимостей
npm install

# Запуск сервера разработки
npm run dev

# Сборка для продакшена
npm run build
```

## 🧩 Структура проекта

```
src/
├── assets/         # Статические ресурсы
├── components/     # Vue компоненты
│   ├── ItemCard.vue                # Карточка вещи
│   ├── UserItemsList.vue          # Список вещей пользователя
│   ├── AvailableItemsList.vue     # Список доступных вещей
│   ├── SelectedUserItems.vue      # Выбранные вещи пользователя
│   └── SelectedAvailableItem.vue  # Выбранная доступная вещь
├── App.vue         # Корневой компонент
└── main.js         # Точка входа
```

## 🎨 Технологии

- **Vue 3**: Прогрессивный JavaScript-фреймворк
- **Vite**: Современный инструмент сборки
- **Composition API**: Использование современного API Vue 3
- **CSS**: Стилизация компонентов с использованием scoped CSS

## 📱 Адаптивность

Приложение адаптировано для различных размеров экранов, включая мобильные устройства.
