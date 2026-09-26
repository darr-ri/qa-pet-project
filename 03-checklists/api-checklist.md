# Чек-лист
## Инструмент: Postman
## Base URL: https://api.qasandbox.org/api
## 1. Аутентификация

### POST /login
- [x] Валидные username + password / 200, есть token
- [ ] Без пароля / 400, "Missing password"
- [x] Без username / 400, "Missing email or username"
- [x] Неверный username / 400, "User not found"
- [x] Пустое тело запроса / 400, "Missing email or username"

### POST /register
- [x] Валидные данные / 201
- [x] Без пароля / 400
- [x] Без username / 400

## 2. Пользователи

### GET /mythology
- [x] Статус 200
- [x] Есть поля: id, name, category, desk, img
- [x] data — массив
- [x] img — рабочая ссылка

### GET /mythology{id}
- [x] Статус 200
- [x] Поля: id, name, category, desk, img 
- [x] id совпадает с запрошенным

### GET mythology{id} (не существует)
- [x] Статус 404
- [x] Тело ответа пустое "{}"

## 3. CRUD

### POST /register
- [x] Статус 201

### PUT /mythology{id}
- [x] Статус 200
- [x] updatedAt присутствует

### PATCH /mythology{id}
- [x] Статус 200
- [x] updatedAt присутствует

### DELETE  /mythology{id}
- [x] Статус 204
- [x] Тело ответа пустое

## 4. Негативные и граничные

- [x] GET /api/mythology/0 / 404
- [x] GET /api/mythology/-1 / 404
- [x] GET /api/mythology/abc / 404
- [x] POST с пустым телом / 400
- [x] Отсутствие обязательных полей

## 5. Общие проверки

- [x] Все ответы в JSON
- [x] Время ответа < 1 сек
- [x] Коды ответов соответствуют REST (200, 201, 204, 400, 404)
- [x] Ошибки содержат понятное сообщение
