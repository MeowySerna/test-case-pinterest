# test-case-pinterest

# Тест-кейсы для проверки регистрации

## Негативные тесты

| **ID тест-кейса** | **Тест-кейс**                                                                                             | **Предусловия**                  | **Шаги**                                                                                                                                                     | **Тестовые данные**                       | **Ожидаемый результат**                                   | **Постусловия**                       | **Фактический результат**                 | **Статус**     |
|-------------------|-----------------------------------------------------------------------------------------------------------|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|-----------------------------------------------------------|----------------------------------------|--------------------------------------------|----------------|
| 001               | Проверка отображения ошибки при вводе email с некорректным символом                                       | Открыта главная страница         | 1. Нажать на кнопку "Регистрация"<br>2. Ввести email<br>3. Ввести пароль<br>4. Ввести дату рождения<br>5. Нажать "Продолжить создание аккаунта"              | `username@domain,com`                    | Появляется сообщение об ошибке для email                   | Очистка полей email, password, birthdate |                                                    |                 |
| 002               | Проверка отображения ошибки при вводе email с неправильным форматом                                       | Открыта главная страница         | 1. Нажать на кнопку "Регистрация"<br>2. Ввести email<br>3. Ввести пароль<br>4. Ввести дату рождения<br>5. Нажать "Продолжить создание аккаунта"              | `username@domain,.com`                   | Появляется сообщение об ошибке для email                   | Очистка полей email, password, birthdate |                                                    |                 |
| 003               | Проверка отображения ошибки при пустом поле email                                                         | Открыта главная страница         | 1. Нажать на кнопку "Регистрация"<br>2. Оставить email пустым<br>3. Ввести пароль<br>4. Ввести дату рождения<br>5. Нажать "Продолжить создание аккаунта"     | Пустой email                              | Появляется сообщение об ошибке для email                   | Очистка полей email, password, birthdate |                                                    |                 |
| 004               | Проверка отображения ошибки при вводе короткого пароля                                                    | Открыта главная страница         | 1. Нажать на кнопку "Регистрация"<br>2. Ввести email<br>3. Ввести короткий пароль<br>4. Ввести дату рождения<br>5. Нажать "Продолжить создание аккаунта"    | `123`                                     | Появляется сообщение об ошибке для пароля                  | Очистка полей email, password, birthdate |                                                    |                 |
| 005               | Проверка отображения ошибки при вводе слабого пароля                                                      | Открыта главная страница         | 1. Нажать на кнопку "Регистрация"<br>2. Ввести email<br>3. Ввести слабый пароль<br>4. Ввести дату рождения<br>5. Нажать "Продолжить создание аккаунта"       | `p@ssw`                                   | Появляется сообщение об ошибке для пароля                  | Очистка полей email, password, birthdate |                                                    |                 |
| 006               | Проверка отображения ошибки при пустом поле пароля                                                        | Открыта главная страница         | 1. Нажать на кнопку "Регистрация"<br>2. Ввести email<br>3. Оставить поле пароля пустым<br>4. Ввести дату рождения<br>5. Нажать "Продолжить создание аккаунта" | Пустой пароль                             | Появляется сообщение об ошибке для пароля                  | Очистка полей email, password, birthdate |                                                    |                 |
| 007               | Проверка отображения ошибки при вводе некорректной даты рождения                                          | Открыта главная страница         | 1. Нажать на кнопку "Регистрация"<br>2. Ввести email<br>3. Ввести пароль<br>4. Ввести некорректную дату рождения<br>5. Нажать "Продолжить создание аккаунта" | `31-02-2000`                              | Появляется сообщение об ошибке для даты рождения          | Очистка полей email, password, birthdate |                                                    |                 |
| 008               | Проверка отображения ошибки при вводе даты рождения с неверным форматом                                   | Открыта главная страница         | 1. Нажать на кнопку "Регистрация"<br>2. Ввести email<br>3. Ввести пароль<br>4. Ввести дату с неверным форматом<br>5. Нажать "Продолжить создание аккаунта"    | `2000-13-01`                              | Появляется сообщение об ошибке для даты рождения          | Очистка полей email, password, birthdate |                                                    |                 |
| 009               | Проверка отображения ошибки при пустом поле даты рождения                                                 | Открыта главная страница         | 1. Нажать на кнопку "Регистрация"<br>2. Ввести email<br>3. Ввести пароль<br>4. Оставить поле даты рождения пустым<br>5. Нажать "Продолжить создание аккаунта" | Пустая дата рождения                      | Появляется сообщение об ошибке для даты рождения          | Очистка полей email, password, birthdate |                                                    |                 |
| 010               | Проверка отображения ошибок при пустых значениях всех полей                                               | Открыта главная страница         | 1. Нажать на кнопку "Регистрация"<br>2. Оставить все поля (email, пароль, дата рождения) пустыми<br>3. Нажать "Продолжить создание аккаунта"                  | Пустые email, пароль и дата рождения      | Появляется сообщение об ошибке для всех полей             | Очистка полей email, password, birthdate |                                                    |                 |

# Тест-кейсы для позитивного тестирования регистрации с различными значениями пароля и даты рождения

| **ID тест-кейса** | **Тест-кейс**                                                                                               | **Предусловия**                  | **Шаги**                                                                                                                                                      | **Тестовые данные**                            | **Ожидаемый результат**                                 | **Постусловия**                         | **Фактический результат**              | **Статус**     |
|-------------------|-------------------------------------------------------------------------------------------------------------|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------|---------------------------------------------------------|------------------------------------------|-----------------------------------------|----------------|
| 001               | Проверка успешной регистрации с валидными данными                                                           | Открыта главная страница         | 1. Нажать на кнопку "Регистрация"<br>2. Ввести валидный email<br>3. Ввести валидный пароль<br>4. Ввести корректную дату рождения<br>5. Нажать "Продолжить создание аккаунта" | `valid@example.com`, `ValidPassword123`, `1990-01-01` | Происходит успешная регистрация и перенаправление на главную страницу | Очистка полей email, password, birthdate | Перенаправление произошло успешно       | Passed         |
| 002               | Проверка успешной регистрации с минимально допустимой длиной пароля                                         | Открыта главная страница         | 1. Нажать на кнопку "Регистрация"<br>2. Ввести валидный email<br>3. Ввести минимально допустимый пароль<br>4. Ввести корректную дату рождения<br>5. Нажать "Продолжить создание аккаунта" | `valid@example.com`, `alidP1`, `1990-01-01`             | Происходит успешная регистрация и перенаправление на главную страницу | Очистка полей email, password, birthdate |                                         |                 |
| 003               | Проверка успешной регистрации с минимально допустимой датой рождения                                        | Открыта главная страница         | 1. Нажать на кнопку "Регистрация"<br>2. Ввести валидный email<br>3. Ввести валидный пароль<br>4. Ввести минимально допустимую дату рождения<br>5. Нажать "Продолжить создание аккаунта" | `valid@example.com`, `ValidPassword123`, `1900-01-01` | Происходит успешная регистрация и перенаправление на главную страницу | Очистка полей email, password, birthdate |                                         |                 |
| 004               | Проверка успешной регистрации с максимально допустимой датой рождения                                       | Открыта главная страница         | 1. Нажать на кнопку "Регистрация"<br>2. Ввести валидный email<br>3. Ввести валидный пароль<br>4. Ввести максимально допустимую дату рождения<br>5. Нажать "Продолжить создание аккаунта" | `valid@example.com`, `ValidPassword123`, `2015-12-31` | Происходит успешная регистрация и перенаправление на главную страницу | Очистка полей email, password, birthdate |                                         |                 |
