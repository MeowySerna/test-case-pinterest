# Тестовая документация для функционала регистрации и авторизации Pinterest

Этот репозиторий содержит тест-кейсы и баг-репорты для функционала регистрации и авторизации пользователей на платформе Pinterest. Тест-кейсы разработаны с использованием техник тест-дизайна, включая эквивалентное разбиение и анализ граничных значений.

## Содержание

1. [Позитивные тест-кейсы для регистрации](#позитивные-тест-кейсы-для-регистрации)
2. [Негативные тест-кейсы для регистрации](#негативные-тест-кейсы-для-регистрации)
3. [Позитивные тест-кейсы для авторизации](#позитивные-тест-кейсы-для-авторизации)
4. [Негативные тест-кейсы для авторизации](#негативные-тест-кейсы-для-авторизации)
5. [Баг-репорты](#баг-репорты)

---

## Позитивные тест-кейсы для регистрации

| **ID тест-кейса** | **Название тест-кейса**                                            | **Предусловия**                  | **Шаги**                                                                                                                                                       | **Тестовые данные**                                | **Ожидаемый результат**                               | **Постусловия**                         | **Статус** |
|-------------------|--------------------------------------------------------------------|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------|-------------------------------------------------------|------------------------------------------|------------|
| TC-REG-001        | Успешная регистрация с валидными данными                          | Открыта главная страница         | 1. Нажать "Регистрация" <br>2. Ввести валидный email, пароль и дату рождения <br>3. Нажать "Продолжить"                   | `user@example.com`, `ValidPass123!`, `1990-01-01` | Переход на главную страницу после успешной регистрации | Очистка полей email, password, birthdate | Passed     |
| TC-REG-002        | Регистрация с минимально допустимым паролем                       | Открыта главная страница         | 1. Нажать "Регистрация" <br>2. Ввести email, минимально допустимый пароль и дату рождения <br>3. Нажать "Продолжить"     | `user@example.com`, `Pwd1!`, `1990-01-01`         | Переход на главную страницу после успешной регистрации | Очистка полей email, password, birthdate | Passed     |
| TC-REG-003        | Регистрация с минимально допустимой датой рождения                | Открыта главная страница         | 1. Нажать "Регистрация" <br>2. Ввести email, пароль и минимальную дату рождения <br>3. Нажать "Продолжить"               | `user@example.com`, `ValidPass123!`, `1900-01-01` | Переход на главную страницу после успешной регистрации | Очистка полей email, password, birthdate | Passed     |
| TC-REG-004        | Регистрация с максимально допустимой датой рождения               | Открыта главная страница         | 1. Нажать "Регистрация" <br>2. Ввести email, пароль и максимальную дату рождения <br>3. Нажать "Продолжить"              | `user@example.com`, `ValidPass123!`, `2005-12-31` | Переход на главную страницу после успешной регистрации | Очистка полей email, password, birthdate | Passed     |

---

## Негативные тест-кейсы для регистрации

| **ID тест-кейса** | **Название тест-кейса**                                                  | **Предусловия**                  | **Шаги**                                                                                                                                                       | **Тестовые данные**                           | **Ожидаемый результат**                               | **Постусловия**                         | **Статус** |
|-------------------|--------------------------------------------------------------------------|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|-------------------------------------------------------|------------------------------------------|------------|
| TC-REG-005        | Регистрация с уже существующим email                                    | Открыта главная страница         | 1. Нажать "Регистрация" <br>2. Ввести уже зарегистрированный email <br>3. Ввести пароль и дату рождения <br>4. Нажать "Продолжить" | `existing@example.com`, `ValidPass123!`, `1990-01-01` | Сообщение о том, что email уже зарегистрирован | Очистка полей email, password, birthdate | Failed     |
| TC-REG-006        | Регистрация с коротким паролем                                          | Открыта главная страница         | 1. Нажать "Регистрация" <br>2. Ввести email <br>3. Ввести слишком короткий пароль <br>4. Ввести дату рождения <br>5. Нажать "Продолжить" | `user@example.com`, `123`, `1990-01-01`       | Сообщение об ошибке при вводе короткого пароля        | Очистка полей email, password, birthdate | Passed     |
| TC-REG-007        | Регистрация с некорректной датой рождения (неверный формат)             | Открыта главная страница         | 1. Нажать "Регистрация" <br>2. Ввести email и пароль <br>3. Ввести некорректную дату рождения <br>4. Нажать "Продолжить" | `user@example.com`, `ValidPass123!`, `31-02-2000` | Сообщение об ошибке при вводе некорректной даты       | Очистка полей email, password, birthdate | Passed     |
| TC-REG-008        | Регистрация с пустыми значениями всех полей                             | Открыта главная страница         | 1. Нажать "Регистрация" <br>2. Оставить все поля пустыми <br>3. Нажать "Продолжить"                                      | Пустые email, пароль, дата рождения           | Сообщения об ошибке для всех пустых полей             | Очистка полей email, password, birthdate | Passed     |

---

## Позитивные тест-кейсы для авторизации

| **ID тест-кейса** | **Название тест-кейса**                                           | **Предусловия**                  | **Шаги**                                                                                                                                                       | **Тестовые данные**                         | **Ожидаемый результат**                               | **Постусловия**                         | **Статус** |
|-------------------|-------------------------------------------------------------------|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|-------------------------------------------------------|------------------------------------------|------------|
| TC-LOGIN-001      | Успешный вход с валидными данными                                 | Открыта главная страница         | 1. Нажать "Вход" <br>2. Ввести email и пароль <br>3. Нажать "Продолжить"                                                | `user@example.com`, `ValidPass123!`         | Переход на главную страницу после успешного входа     | Очистка полей email и password          | Passed     |

---

## Негативные тест-кейсы для авторизации

| **ID тест-кейса** | **Название тест-кейса**                                           | **Предусловия**                  | **Шаги**                                                                                                                                                       | **Тестовые данные**                         | **Ожидаемый результат**                               | **Постусловия**                         | **Статус** |
|-------------------|-------------------------------------------------------------------|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|-------------------------------------------------------|------------------------------------------|------------|
| TC-LOGIN-002      | Вход с некорректным паролем                                      | Открыта главная страница         | 1. Нажать "Вход" <br>2. Ввести email и некорректный пароль <br>3. Нажать "Продолжить"                                   | `user@example.com`, `WrongPass`             | Сообщение об ошибке при неправильном пароле           | Очистка полей email и password          | Passed     |
| TC-LOGIN-003      | Вход с пустыми значениями email и пароля                          | Открыта главная страница         | 1. Нажать "Вход" <br>2. Оставить email и пароль пустыми <br>3. Нажать "Продолжить"                                      | Пустые email и пароль                       | Сообщения об ошибке для пустых полей                  | Очистка полей email и password          | Passed     |
| TC-LOGIN-004      | Вход с незарегистрированным email                                | Открыта главная страница         | 1. Нажать "Вход" <br>2. Ввести незарегистрированный email и корректный пароль <br>3. Нажать "Продолжить"                | `notregistered@example.com`, `ValidPass123!` | Сообщение об ошибке о неверных данных для входа       | Очистка полей email и password          | Passed     |

---


## Баг-репорты

| **ID**                       | BR-001 |
|------------------------------|--------|
| **Заголовок**                | Система допускает регистрацию с уже зарегистрированным email на Pinterest |
| **Краткое описание**         | При вводе корректного пароля и уже зарегистрированного email в форму регистрации на Pinterest происходит переход на главную страницу, вместо отображения сообщения об ошибке о том, что email уже зарегистрирован. |
| **Шаги для воспроизведения** | 1. Перейти на страницу регистрации Pinterest.<br>2. Ввести email, который уже зарегистрирован в системе.<br>3. Ввести корректный пароль, соответствующий требованиям.<br>4. Нажать на кнопку "Продолжить создание аккаунта". |
| **Ожидаемый результат**      | Отображается сообщение об ошибке, информирующее пользователя о том, что указанный email уже зарегистрирован, и предлагается выполнить вход или восстановление пароля. |
| **Фактический результат**    | Происходит переход на главную страницу, как если бы регистрация прошла успешно, вместо сообщения об ошибке. |
| **Серьезность (Severity)**   | Средняя (Medium) |
| **Приоритет (Priority)**     | Высокий (High) — данный баг создает путаницу для пользователей, так как они могут думать, что аккаунт зарегистрирован повторно. |
| **Окружение**                | - **Браузер:** Google Chrome <br>- **ОС:** Windows 11 <br> |
| **Дополнительные сведения**  | Данная проблема может вызвать негативный пользовательский опыт, так как неинформативное поведение системы приводит к ложному восприятию успешной регистрации. |

