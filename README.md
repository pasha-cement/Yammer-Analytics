# Yammer Analytics

Учебный проект по анализу данных социальной корпоративной сети Yammer. Набор данных предназначен для практики SQL и A/B тестированя на реальных по структуре, но синтетических данных.

## Данные

Все CSV-файлы находятся в папке [`yammer`](yammer).

| Файл | Описание | Количество строк |
| --- | --- | ---: |
| [`users.csv`](yammer/users.csv) | Пользователи и сведения об их аккаунтах | 19 066 |
| [`events.csv`](yammer/events.csv) | Все события пользователей; объединяет `events1.csv`, `events2.csv` и `events3.csv` | 340 832 |
| [`emails.csv`](yammer/emails.csv) | Отправка и взаимодействие с email-рассылками | 90 389 |
| [`experiments.csv`](yammer/experiments.csv) | Участники экспериментов и группы тестирования | 2 595 |

Количество строк указано вместе с заголовком.

### `users.csv`

| Поле | Описание |
| --- | --- |
| `user_id` | Уникальный идентификатор пользователя |
| `created_at` | Дата создания аккаунта |
| `company_id` | Идентификатор компании пользователя |
| `language` | Язык пользователя |
| `activated_at` | Дата активации аккаунта; может быть пустой |
| `state` | Состояние аккаунта: `active` или `pending` |

### `events.csv`

| Поле | Описание |
| --- | --- |
| `user_id` | Пользователь, совершивший действие |
| `occurred_at` | Дата и время события |
| `event_type` | Общий тип события: `signup_flow` или `engagement` |
| `event_name` | Конкретное действие, например `login`, `home_page`, `send_message` или `search_run` |
| `location` | Страна, определенная по IP-адресу |
| `device` | Устройство пользователя |
| `user_type` | Тип пользователя |

Основные значения `event_name` включают `login`, `home_page`, `like_message`, `send_message`, `view_inbox`, `search_run`, `search_autocomplete` и `search_click_result_X`.

### `emails.csv`

| Поле | Описание |
| --- | --- |
| `user_id` | Пользователь, которому относится событие |
| `occurred_at` | Дата и время события |
| `action` | Действие: `sent_weekly_digest`, `sent_reengagement_email`, `email_open` или `email_clickthrough` |
| `user_type` | Тип пользователя |

### `experiments.csv`

| Поле | Описание |
| --- | --- |
| `user_id` | Участник эксперимента |
| `occurred_at` | Дата и время записи об эксперименте |
| `experiment` | Название эксперимента; в текущем наборе данных — `publisher_update` |
| `experiment_group` | Группа эксперимента: `control_group` или `test_group` |
| `location` | Страна пользователя |
| `device` | Устройство пользователя |
| `user_type` | Тип пользователя |