# Чек-лист
## Инструмент: Postman
## Base URL: https://reqres.in/api
## 1. Аутентификация

### POST /api/login
- [ ] Валидные email + password / 200, есть token
- [x] Без пароля / 400, "Missing password"
- [x] Без email / 400, "Missing email or username"
- [x] Неверный email / 400, "User not found"
- [x] Пустое тело запроса / 400, "Missing email or username"

### POST /api/register
- [ ] Валидные данные / 200, id + token
- [x] Без пароля / 400
- [x] Без email / 400

## 2. Пользователи

### GET /api/users?page=2
- [x] Статус 200
- [x] Есть поля: page, per_page, total, total_pages, data
- [x] data — массив
- [x] У каждого элемента: id, email, first_name, last_name, avatar
- [x] email в валидном формате
- [x] avatar — рабочая ссылка

### GET /api/users/2
- [x] Статус 200
- [x] Поля: data.id, data.email, data.first_name, data.last_name, data.avatar
- [x] id совпадает с запрошенным

### GET /api/users/23 (не существует)
- [x] Статус 404
- [x] Тело ответа пустое "{}"

## 3. CRUD

### POST /api/users
- [x] Статус 201
- [x] Есть id и createdAt

### PUT /api/users/2
- [x] Статус 200
- [x] updatedAt присутствует

### PATCH /api/users/2
- [x] Статус 200
- [x] updatedAt присутствует

### DELETE /api/users/2
- [x] Статус 204
- [x] Тело ответа пустое

## 4. Негативные и граничные

- [x] GET /api/users/0 / 404
- [x] GET /api/users/-1 / 404
- [x] GET /api/users/abc / 404
- [x] POST с пустым телом / 400
- [x] Отсутствие обязательных полей

## 5. Общие проверки

- [x] Все ответы в JSON
- [x] Время ответа < 1 сек
- [x] Коды ответов соответствуют REST (200, 201, 204, 400, 404)
- [x] Ошибки содержат понятное сообщение
