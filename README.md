# Тестовое задание

**Ожидаемый результат:** необходимо разработать API-приложение для доступа к сделкам и их контактам amoCRM (read-only),
а также сделать небольшое *представление,* которое будет использовать данный API

## Frontend

- Vue 3, c предпочтительным использованием **Typescript**
- Желательно использовать UI-kit [Antd](https://www.antdv.com/) или любой другой
- HTML-рендер можно осуществлять как на сервере, так и на клиенте (полный или частичный, в любых "пропорциях")
- Главное - минимальный user-friendly интерфейс и чтобы ваше представление отображало всю необходимую информацию (как в
  примере). Одним словом, нужно "сделать красиво" ~~и поиграться со шрифтами~~, чувство прекрасного **очень
  приветствуется**, но сильно не переусердствуйте с дизайном хотя бы для экономии своего времени 😉

## Backend (не обязательно, но будет плюсом)

Запросы к amoCRM можно сделать и из Frontend,
используя [Долгосрочные токены](https://www.amocrm.ru/developers/content/oauth/step-by-step#%D0%94%D0%BE%D0%BB%D0%B3%D0%BE%D1%81%D1%80%D0%BE%D1%87%D0%BD%D1%8B%D0%B5-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D1%8B) -
но если мы говорим про production решение - запросами к amoCRM должен заниматься выделенный backend.

- Приложение необходимо сделать на платформе [NodeJS](https://nodejs.org/en/), с использованием NestJS (предпочтительно)
  или Express. **Typescript будет большим плюсом!**
- Разрабатываемому приложению будет достаточно одного GET-эндпоинта (например, `/api/leads`)
- Эндпоинт по-умолчанию отдаёт все сделки и прикреплённые к ним контакты, но при наличии GET-параметра `query` (от трёх
  символов) отдача должна производиться с учётом фильтрации

    <aside>
    💡 **Подсказка**
    Не нужно изобретать свои алгоритмы фильтрации, воспользуйтесь [имеющимися возможностями amoCRM](https://www.amocrm.ru/developers/content/crm_platform/api-reference)

    </aside>

- Разработанное API-приложение не подразумевает **собственной** авторизации/аутентификации, то есть backend должен
  возвращать ответ на любой "анонимный" запрос

## Пример

Ознакомиться с примером работы можно [здесь](https://test-task.rocket.red) (работает 24/7, но это не точно)

## Подсказки

- Демо-аккаунт

  Для выполнения тестового задания необходим аккаунт в amoCRM, зарегистрировать демо-аккаунт
  можно [здесь](https://www.amocrm.ru/) (нажмите на кнопку "Пробная версия"), триал длится 14 дней, этого должно хватить
  😉

    - Создание интеграции

  ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/7f6dcf90-1339-4995-a4db-bcf6c40930b2/f45ab0ec-dbba-42e4-8579-cc8257601b13/Untitled.png)

- Упрощённая авторизация amoCRM (для запросов к API)

  Для существенной экономии времени, при разработке приложения
  используйте [упрощённый способ авторизации](https://www.amocrm.ru/developers/content/oauth/easy-auth)

- Фильтрация сущностей

  Для фильтрации сущностей, используйте GET-параметр `query`. Этот параметр необходимо слать на ваше API-приложение,
  которое, в свою очередь, аналогично будет использовать его в качестве параметра при формировании запроса к API amoCRM

  !https://prod-files-secure.s3.us-west-2.amazonaws.com/7f6dcf90-1339-4995-a4db-bcf6c40930b2/6182b59c-e96c-4bb3-aeee-b8b279bcd324/Untitled.png

- Статусы сделок

  Чтобы узнать название воронки и статусов сделок,
  воспользуйтесь [данным методом](https://www.amocrm.ru/developers/content/crm_platform/leads_pipelines) API amoCRM

- Ответственные менеджеры

  Чтобы узнать имя ответственного менеджера,
  воспользуйтесь [данным методом](https://www.amocrm.ru/developers/content/crm_platform/users-api) API amoCRM

## Формат сдачи

Исходники можно поместить в любое, удобное для вас, хранилище:

1. GitHub
2. GitLab

и отправить в нашу [**форму обратной связи**](https://vk.cc/cxBnTW).

## Материалы

1. [Документация для разработчиков amoCRM](https://amocrm.ru/developers/content/crm_platform/api-reference)
    - [Упрощённая авторизация](https://www.amocrm.ru/developers/content/oauth/easy-auth)
    - [Долгосрочные токены](https://www.amocrm.ru/developers/content/oauth/step-by-step#%D0%94%D0%BE%D0%BB%D0%B3%D0%BE%D1%81%D1%80%D0%BE%D1%87%D0%BD%D1%8B%D0%B5-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D1%8B)
    - [Сделки](https://www.amocrm.ru/developers/content/crm_platform/leads-api)
    - [Контакты](https://www.amocrm.ru/developers/content/api/recommendations)
    - [Воронки и этапы](https://www.amocrm.ru/developers/content/crm_platform/leads_pipelines)
    - [Пользователи](https://www.amocrm.ru/developers/content/crm_platform/users-api)

[Оригинальное Тестовое задание для JavaScript разработчика](https://www.notion.so/JavaScript-c0bc4dab03ed4d8e9c3f628493803212?pvs=21)