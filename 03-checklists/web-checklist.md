# Чек-лист
## 1. Авторизация

### 1.1. Позитивные проверки
- [x] Вход с standard_user / secret_sauce
- [x] Вход с problem_user / secret_sauce
- [x] Вход с performance_glitch_user / secret_sauce
- [x] Вход с error_user / secret_sauce
- [x] Вход с visual_user / secret_sauce
- [x] После входа URL = /inventory.html
- [x] Логотип Swag Labs отображается
- [x] Кнопка Login активна при заполненных полях

### 1.2. Негативные проверки
- [x] Вход с locked_out_user / "Sorry, this user has been locked out"
- [x] Пустой логин / "Username is required"
- [x] Пустой пароль / "Password is required"
- [x] Пустые оба поля / "Username is required"
- [x] Неверный логин / "Username and password do not match any user in this service"
- [x] Неверный пароль / "Username and password do not match any user in this service"
- [x] Логин с пробелами в начале/конце / "Username and password do not match any user in this service"
- [x] Логин в верхнем регистре (STANDARD_USER) / "Username and password do not match any user in this service"
- [x] Логин длиной 1 символ / "Username and password do not match any user in this service"
- [x] Логин длиной 40 символов / "Username and password do not match any user in this service"
- [x] Логин длиной 41+ символов / "Username and password do not match any user in this service"

### 1.3. Безопасность
- [x] Пароль скрыт символами *

### 1.4. UI
- [x] Placeholder в полях "Username", "Password"
- [x] Кнопка Login зеленого цвета
- [x] Сообщение об ошибке красное, с иконкой
- [x] Табуляция работает между полями
- [x] Enter в поле пароля отправляет форму
- [x] Логотип и заголовок по центру

### 1.5. Logout 
- [x] Logout через меню
- [x] После logout - редирект на страницу логина
- [x] После logout кнопка "Назад" не возвращает в каталог 
## 2. Каталог товаров

### 2.1. Отображение
- [x] Отображается 6 товаров
- [x] У каждого товара: изображение, название, описание, цена, кнопка Add to cart
- [x] Цены в формате $XX.XX
- [x] Названия товаров не обрезаны
- [x] Изображения загружаются
- [x] Заголовок «Products» отображается

### 2.2. Сортировка
- [x] Name (A to Z) — сортировка по возрастанию
- [x] Name (Z to A) — сортировка по убыванию
- [x] Price (low to high) — сортировка по возрастанию цены
- [x] Price (high to low) — сортировка по убыванию цены
- [x] Сортировка работает после добавления в корзину
- [ ] Выбранная сортировка сохраняется при переходе в корзину и обратно

### 2.3. Корзина (из каталога)
- [x] Кнопка Add to cart меняется на Remove
- [x] Счётчик корзины увеличивается
- [x] Повторный клик Remove убирает товар и уменьшает счётчик
- [x] Можно добавить все 6 товаров
- [x] Счётчик показывает 6 при добавлении всех

## 3. Карточка товара
- [x] Клик по названию товара открывает карточку
- [x] URL меняется на /inventory-item.html?id=X
- [x] Отображаются: изображение, название, описание, цена
- [x] Кнопка Add to cart / Remove работает
- [x] Кнопка «Back to products» возвращает в каталог
## 4. Корзина

### 4.1. Содержимое
- [x] Все добавленные товары отображаются
- [x] У каждого товара: название, описание, цена, кнопка Remove
- [x] Счётчик в иконке корзины совпадает с количеством товаров
- [x] Кнопка Checkout отображается
- [x] Кнопка Continue Shopping возвращает в каталог

### 4.2. Удаление
- [x] Удаление товара из корзины
- [x] Счётчик уменьшается
- [x] Удаление всех товаров / корзина пуста

### 4.3. Сохранение
- [x] Корзина сохраняется при переходе на карточку товара и обратно
- [x] Корзина сохраняется при перезагрузке страницы
- [x] Корзина сохраняется при logout и повторном входе
## 5. Оформление заказа

### 5.1. Step 1: Your Information
- [x] Поля First Name, Last Name, Zip/Postal Code отображаются
- [x] Пустое First Name / "First Name is required"
- [x] Пустое Last Name / "Last Name is required"
- [x] Пустой Zip / "Postal Code is required"
- [x] Кнопка Continue работает при валидных данных
- [x] Кнопка Cancel возвращает в корзину

### 5.2. Step 2: Overview
- [x] Отображается список товаров
- [x] Отображается Payment Information
- [x] Отображается Shipping Information
- [x] Отображается Price Total (Item total, Tax, Total)
- [x] Сумма Total = Item total + Tax
- [x] Кнопка Finish завершает заказ
- [x] Кнопка Cancel возвращает в каталог

### 5.3. Complete
- [x] Отображается "Thank you for your order!"
- [x] Текст «Your order has been dispatched...»
- [x] Кнопка Back Home возвращает в каталог
- [x] Корзина пуста после заказа
- [x] Счётчик корзины = 0

## 6. Меню

- [x] Открывается по клику
- [x] All Items / каталог
- [ ] About / внешняя ссылка
- [x] Logout / выход
- [x] Reset App State / сброс корзины и счётчика
- [x] Кнопка закрытия (X) работает
## 7. Кросс-браузерное тестирование

- [x] Chrome: весь функционал работает
- [x] Yandex: весь функционал работает
- [x] Вёрстка не ломается во всех браузерах
- [x] Сообщения об ошибках одинаковы
## 8. Нефункциональное

- [x] Время загрузки страницы < 3 сек
- [x] Адаптивность при 1280×720
- [x] Адаптивность при 1920×1080
- [x] Нет ошибок в консоли DevTools
- [x] Нет 404 при загрузке ресурсов (Network tab)
