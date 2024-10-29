# Playbook for Installing Clickhouse and Vector

Этот playbook предназначен для установки и настройки Clickhouse и Vector на указанных хостах. Он автоматически загружает необходимые пакеты, устанавливает их и запускает соответствующие сервисы.

## Описание задач

### 1. Установка Clickhouse
Playbook выполняет следующие шаги для установки Clickhouse:
- Загружает дистрибутивы Clickhouse из официального репозитория (с поддержкой резерва на случай неудачной загрузки).
- Устанавливает пакеты Clickhouse (`clickhouse-common-static`, `clickhouse-client`, `clickhouse-server`).
- Запускает сервис Clickhouse после установки.
- Создаёт базу данных `logs` (игнорирует ошибку, если база уже существует).

### 2. Установка Vector
Playbook выполняет следующие шаги для установки Vector:
- Загружает дистрибутив Vector из официального репозитория.
- Устанавливает пакет Vector.
- Запускает сервис Vector после установки.

## Переменные

- **`clickhouse_version`**: Версия Clickhouse, которая будет установлена.
- **`clickhouse_packages`**: Список пакетов Clickhouse для загрузки и установки (например, `clickhouse-common-static`, `clickhouse-client`, `clickhouse-server`).
- **`vector_version`**: Версия Vector, которая будет установлена.

## Теги

- **`clickhouse`**: Тег для выполнения задач, связанных с установкой Clickhouse.
- **`vector`**: Тег для выполнения задач, связанных с установкой Vector.

## Использование

Для запуска playbook'а используйте следующую команду:

```bash
ansible-playbook playbook.yml -i inventory.yml
