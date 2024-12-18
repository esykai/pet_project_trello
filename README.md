# Task Management API

Этот проект представляет собой API для управления задачами. Он позволяет создавать, читать, обновлять и удалять задачи через HTTP-запросы. API разработан с использованием стандартных методов HTTP и предоставляет базовые функции для работы с задачами.

## Функции API

1. **Создание задачи**  
   Вы можете создать новую задачу с помощью `POST` запроса.

2. **Получение задачи**  
   Используйте `GET` запрос для получения задачи по ее идентификатору.

3. **Обновление задачи**  
   С помощью `PUT` запроса можно обновить данные существующей задачи.

4. **Удаление задачи**  
   Задачу можно удалить с помощью `DELETE` запроса.

## Как запустить проект

1. Клонируйте репозиторий:
    ```bash
    git clone https://github.com/esykai/pet_project_trello.git
    ```

2. Перейдите в директорию проекта:
    ```bash
    cd pet_project_trello
    ```

3. Установите необходимые зависимости:
    ```bash
    pip install -r requirements.txt
    ```

4. Запустите сервер:
    ```bash
    uvicorn main:app --reload
    ```

Теперь сервер будет доступен по адресу `http://127.0.0.1:8000`.

## Пример использования

### 1. Создание задачи

`POST /tasks/`

**Запрос:**
```json
{
    "title": "New Task",
    "description": "This is a test task.",
    "status": "pending"
}
```
**Ответ:**
```json
{
    "id": 1,
    "title": "New Task",
    "description": "This is a test task.",
    "status": "pending"
}
```

### 2. Получение задачи по ID

`GET /tasks/{task_id}`

**Ответ:**
```json
{
    "id": 1,
    "title": "New Task",
    "description": "This is a test task.",
    "status": "pending"
}
```

### 3. Обновление задачи

`PUT /tasks/{task_id}`

**Запрос:**
```json
{
    "title": "Updated Task",
    "description": "This task has been updated.",
    "status": "in_progress"
}
```

**Ответ:**
```json
{
    "id": 1,
    "title": "Updated Task",
    "description": "This task has been updated.",
    "status": "in_progress"
}
```

### 4. Удаление задачи

`DELETE /tasks/{task_id}

**Ответ:**
```json
{
    "message": "Task deleted successfully"
}
```

## Проверка работоспособности через `tests/basic_tests.py`

В файле `tests/basic_tests.py` содержатся тесты для проверки основной функциональности API. Этот файл можно использовать для проверки работоспособности всех ключевых операций API, таких как создание, получение, обновление и удаление задач.

### Что можно проверить:

1. **Создание задачи**  
   Тестирует работу эндпоинта `POST /tasks/` для создания новой задачи с нужными параметрами.

2. **Получение задачи по ID**  
   Тестирует работу эндпоинта `GET /tasks/{task_id}`, проверяя правильность получения задачи по ID.

3. **Обновление задачи**  
   Тестирует работу эндпоинта `PUT /tasks/{task_id}` для обновления данных существующей задачи.

4. **Удаление задачи**  
   Тестирует работу эндпоинта `DELETE /tasks/{task_id}` для удаления задачи.