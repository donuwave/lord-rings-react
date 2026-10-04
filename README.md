# 💍 The Lord of the Rings — справочник персонажей

Каталог персонажей «Властелина колец» на [The One API](https://the-one-api.dev): поиск, фильтры по расам, сортировка, страница персонажа с цитатами из фильмов, избранное и история поиска в личном кабинете.

Проект сделан на **стажировке в компании LAD** по техническому заданию. ТЗ проверяло работу с React, Redux Toolkit, RTK Query, Firebase, Storybook и feature flags.

## Возможности

**Каталог**
- Поиск персонажей по имени с подсказками
- Фильтр по расам и сортировка по имени
- Пагинация
- Переключение вида карточек: сетка или список
- Поделиться персонажем в Telegram (включается через feature flag с сервера)

**Персонаж**
- Подробная информация о персонаже
- Цитаты персонажа с указанием фильма

**Аккаунт** (Firebase)
- Регистрация, вход и восстановление пароля
- Приватные роуты: страницы персонажа, избранного и истории доступны только после входа
- Избранное: добавление и удаление лайком
- История поисковых запросов: переход по запросу, удаление по одному или всех сразу
- Избранное и история синхронизируются с Firestore и сохраняются между сессиями

## Что применено

- Функциональные компоненты и кастомные хуки, разделение на умные и презентационные компоненты
- Формы на **React Hook Form**
- **Context API**, **Error Boundary**, **lazy + Suspense** для страниц
- **Redux Toolkit**: слайсы, `redux-persist`
- **RTK Query** с `transformResponse`: ответы API приводятся к своему формату через конвертеры
- **Кастомный middleware**, который синхронизирует избранное и историю с Firebase при изменении стора
- **Feature flags**: флаги отдаёт небольшой Express-сервер, клиент читает их при старте
- **Storybook** для UI-компонентов
- TypeScript, PropTypes

## Стек

![React](https://img.shields.io/badge/React_18-20232A?style=flat&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Redux Toolkit](https://img.shields.io/badge/Redux_Toolkit-764ABC?style=flat&logo=redux&logoColor=white)
![React Router](https://img.shields.io/badge/React_Router-CA4245?style=flat&logo=react-router&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat&logo=firebase&logoColor=black)
![styled-components](https://img.shields.io/badge/styled--components-DB7093?style=flat&logo=styled-components&logoColor=white)
![Storybook](https://img.shields.io/badge/Storybook-FF4785?style=flat&logo=storybook&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat&logo=express&logoColor=white)

React 18, TypeScript, Redux Toolkit + RTK Query, redux-persist, React Router, React Hook Form, Firebase (Auth + Firestore), styled-components, MUI, Framer Motion, react-toastify, Storybook, Express

## Запуск

Для запуска нужен ключ [The One API](https://the-one-api.dev/sign-up) и проект в Firebase.

```bash
git clone https://github.com/donuwave/lord-rings-react.git
cd lord-rings-react
npm install
```

Создай `.env` в корне:

```
REACT_APP_API=ключ_the_one_api

REACT_APP_FIREBASE_API_KEY=
REACT_APP_FIREBASE_AUTH_DOMAIN=
REACT_APP_FIREBASE_PROJECT_ID=
REACT_APP_FIREBASE_STORAGE_BUCKET=
REACT_APP_FIREBASE_MESSAGING_SENDER_ID=
REACT_APP_FIREBASE_API_ID=
```

Запуск:

```bash
# сервер с feature flags (порт 5000)
cd server && npm install && npm run start

# клиент
npm run start

# Storybook
npm run storybook
```
