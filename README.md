# План автоматизации тестирования отправки [формы](https://netology.ru/programs/qa#/order) для записи на курс "[Тестировщик ПО](https://netology.ru/programs/qa#/)"
___
Настоящий план предполагает автоматизацию функционального юнит-тестирования заполнения и отправки формы регистрации путем позитивных и негативных проверок.
## 1. Сценарии для автоматизации:
### Переход к странице курса:
1. Главная страница сайта -> Каталог курсов -> Раздел "Программирование" -> "Тестировщик ПО"
2. Главная страница сайта -> Каталог курсов -> Ссылка "Полный каталог" -> Фильтр "Программирование" -> "Тестировщик ПО"
3. Главная страница сайта -> Каталог курсов -> Ссылка "Полный каталог" -> Поисковой запрос "тестировщик" -> "Тестировщик ПО"
4. Главная страница сайта -> Раздел "**нео** для начинающих" -> Фильтр "Программирование" -> "Тестировщик ПО"
5. Главная страница сайта -> Раздел "**нео** для начинающих" -> Поисковой запрос "тестировщик" -> "Тестировщик ПО"
6. Главная страница сайта -> Раздел "Изучайте актуальные темы" -> Раздел "Программирование" -> "Тестировщик ПО"
**Ожидаемый результат:** в браузере отображается страница курса "[Тестировщик ПО](https://netology.ru/programs/qa#/)".
### Переход к форме со страницы курса:
1. Страница курса "Тестировщик" -> Кнопка "Записаться" в верхней части страницы под маркированным списком
2. Страница курса "Тестировщик" -> Кнопка "Записаться" в разделе "**Гарантия возврата денег**"
3. Страница курса "Тестировщик" -> Скролл вниз до раздела "**Запишитесь или получите консультацию**"
**Ожидаемый результат:** в браузере отображается форма регистрации для заполнения.
### Заполнение формы:
1. **Валидные данные:**
   * *Имя:* от 2 символов кириллицей или латиницей + с использованием пробелов или дефисов
   * *Телефон:* от 9 до 14 цифр + с использованием символов "+", "-", "(" и ")"
   **Ожидаемый результат:** данные из формы отправляются на сервер, отображается уведомление об успешной регистрации.
2. **Пустые поля:**
    * Оба поля пустые
    * Поле "Имя" пустое, поле "Телефон" с валидными данными
    * Поле "Телефон" пустое, поле "Имя" с валидными данными
    **Ожидаемый результат:** данные из формы не отправляются, отображается сообщение об обязательном заполнении соответствующих полей.
3. **Невалидные данные:**
   * *Имя:* менее 2 символов, с использованием цифр и специальных символов
   * *Телефон:* менее 9 и более 14 цифр + с использованием букв и специальных символов, кроме "+", "-", "(" и ")"
   **Ожидаемый результат:** данные из формы не отправляются, отображается сообщение о необходимом формате данных в соответствующих полях.
## 2. Необходимые инструменты:
* **Java** - для написания кода авто-тестов
* **Gradle** - для сборки и конфигурации проекта с авто-тестами
* **JUnit 5** - для настройки авто-тестов
* **Project Lombok** - для упрощения написания кода авто-тестов
* **JavaFaker** - для случайной генерации тестовх данных для заполнения формы
* **Selenium** или **Selenide** - для взаимодействия тестов с веб-интерфейсом
* Популярные браузеры (**Google Chrome, Mozilla Firefox, Opera, Safari**) для кросс-браузерного тестирования
* **DBeaver** или любая другая программа для работы с базами данных
* **Allure** - для генерации подробных отчетов о прохождении авто-тестов
## 3. Необходимые разрешения:
Для максимального покрытия и корректной работы авто-тестов необходимы:
* Разрешение от владельца продукта на выполнение автоматизированного тестирования рабочего сайта
* Доступ к базе данных, в которую записывается информация после отправки формы
* Возможность отправлять API-запросы для тестирования отправки данных не через веб-интерфейс
## 4. Анализ возможных рисков:
1. При проведении тестирования через веб-интерфейс могут возникнуть сложности с поиском локаторов, необходимых для автоматического заполнения и отправки формы
2. При проведении тестирования на тестовом окружении необходимо удостовериться, что поведение будет идентично релизной версии.
3. При проведении тестирования на релизном окружении необходимо удостовериться, что оно справится с большим количеством запросов.
4. При проведении тестирования на релизном окружении необходимо удостовериться, что авто-тесты не повлияют на текущую функциональность сайта.
5. Исключить возможность утечки данных для доступа к базе данных.
6. Исключить возможность XSS-атак на релизном окружении.
## 5. Необходимые специалисты:
* Специалист по автоматизации тестирования для подготовки и реализации авто-тестов
## 6. Необходимое время:
#### Предварительная оценка необходимого времени на автоматизацию тестирования с учётом рисков: от 24 до 48 часов
