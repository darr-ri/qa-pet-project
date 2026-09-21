# Чек-лист
## 1. Аутентификация

### POST /api/login
- [ ] Валидные email + password → 200, есть token
- [ ] Без пароля → 400, «Missing password»
- [ ] Без email → 400, «Missing email or username»
- [ ] Неверный email → 400
- [ ] Пустое тело запроса → 400
- [ ] Невалидный JSON → 400
- [ ] Content-Type: application/json соблюдён

### POST /api/register
- [ ] Валидные данные → 200, id + token
- [ ] Без пароля → 400
- [ ] Без email → 400

## 2. Пользователи

### GET /api/users?page=2
- [ ] Статус 200
- [ ] Есть поля: page, per_page, total, total_pages, data
- [ ] data — массив
- [ ] У каждого элемента: id, email, first_name, last_name, avatar
- [ ] email в валидном формате
- [ ] avatar — рабочая ссылка

### GET /api/users/2
- [ ] Статус 200
- [ ] Поля: data.id, data.email, data.first_name, data.last_name
- [ ] id совпадает с запрошенным

### GET /api/users/23 (не существует)
- [ ] Статус 404
- [ ] Тело ответа пустое `{}`

## 3. CRUD

### POST /api/users
- [ ] Статус 201
- [ ] Есть id и createdAt
- [ ] name и job совпадают с отправленными

### PUT /api/users/2
- [ ] Статус 200
- [ ] updatedAt присутствует
- [ ] name и job обновлены

### PATCH /api/users/2
- [ ] Статус 200
- [ ] Обновляется только переданное поле

### DELETE /api/users/2
- [ ] Статус 204
- [ ] Тело ответа пустое

## 4. Негативные и граничные

- [ ] GET /api/users/0 → 404
- [ ] GET /api/users/-1 → 404
- [ ] GET /api/users/abc → 404
- [ ] POST с пустым телом → 400
- [ ] POST с очень длинным name (1000+ символов)
- [ ] Передача SQL-инъекции в name
- [ ] Передача XSS в name
- [ ] Неверный Content-Type (text/plain) → 400
- [ ] Отсутствие обязательных полей

## 5. Общие проверки

- [ ] Все ответы в JSON
- [ ] Заголовок Content-Type: application/json
- [ ] Время ответа ≤ 1 сек
- [ ] Коды ответов соответствуют REST (200, 201, 204, 400, 404)
- [ ] Ошибки содержат понятное сообщение
