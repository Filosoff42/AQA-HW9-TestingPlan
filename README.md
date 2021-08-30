# План автоматизации тестирования отправки [формы](https://netology.ru/programs/qa#/order) для записи на курс "[Тестировщик ПО](https://netology.ru/programs/qa#/)"
___
## 1. Сценарии для автоматизации:
### Переход к странице курса:
1. Главная страница сайта -> Каталог курсов -> Раздел "Программирование" -> "Тестировщик ПО"
2. Главная страница сайта -> Каталог курсов -> Ссылка "Полный каталог" -> Фильтр "Программирование" -> "Тестировщик ПО"
3. Главная страница сайта -> Каталог курсов -> Ссылка "Полный каталог" -> Поисковой запрос "тестировщик" -> "Тестировщик ПО"
4. Главная страница сайта -> Раздел "**нео** для начинающих" -> Фильтр "Программирование" -> "Тестировщик ПО"
5. Главная страница сайта -> Раздел "**нео** для начинающих" -> Поисковой запрос "тестировщик" -> "Тестировщик ПО"
6. Главная страница сайта -> Раздел "Изучайте актуальные темы" -> Раздел "Программирование" -> "Тестировщик ПО"
### Переход к форме со страницы курса:
1. Страница курса "Тестировщик" -> Кнопка "Записаться" в верхней части страницы под маркированным списком
2. Страница курса "Тестировщик" -> Кнопка "Записаться" в разделе "**Гарантия возврата денег**"
3. Страница курса "Тестировщик" -> Скролл вниз до раздела "**Запишитесь или получите консультацию**"
### Заполнение формы:
1. **Валидные данные:**
   * *Имя:* от 2 символов кириллицей или латиницей + с использованием пробелов или дефисов
   * *Телефон:* от 9 до 14 цифр + с использованием символов "+", "-", "(" и ")"
2. **Пустые поля:**
    * Оба поля пустые
    * Поле "Имя" пустое, поле "Телефон" с валидными данными
    * Поле "Телефон" пустое, поле "Имя" с валидными данными
3. **Невалидные данные:**
   * *Имя:* менее 2 символов, с использованием цифр и специальных символов
   * *Телефон:* менее 9 и более 14 цифр + с использованием букв и специальных символов, кроме "+", "-", "(" и ")"
## 2. Необходимые инструменты:
* **Java** - для написания кода авто-тестов
* **Selenium** или **Selenide** - для взаимодействия тестов с веб-интерфейсом
* Популярные браузеры (**Google Chrome, Mozilla Firefox, Opera, Safari**) для кросс-браузерного тестирования
* **DBeaver** или любая другая программа для работы с базами данных
## 3. Необходимые разрешения:
Для максимального покрытия и корректной работы авто-тестов необходимы:
* Доступ к базе данных, в которую записывается информация после отправки формы
* Возможность отправлять API-запросы для тестирования отправки данных не через веб-интерфейс
## 4. Анализ возможных рисков:
1. При проведении тестирования на тестовом окружении необходимо удостовериться, что поведение будет идентично релизной версии.
2. При проведении тестирования на релизном окружении необходимо удостовериться, что оно справится с большим количеством запросов.
3. Исключить возможность утечки данных для доступа к базе данных.
4. Исключить возможность XSS-атак на релизном окружении.
## 5. Необходимые специалисты:
* Специалист по автоматизации тестирования для подготовки авто-тестов
* Frontend-разработчик для консультаций по вопросам веб-интерфейса
* Backend-разработчик для консультаций и организации доступа к базе данных и API
## 6. Необходимое время:
#### Предварительная оценка необходимого времени на автоматизацию тестирования с учётом рисков: от 24 до 48 часов
