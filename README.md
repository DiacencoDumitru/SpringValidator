* Будем валидировать данные, если у нас уже существует такой email. Тогда мы обработаем её в с
  помощью `Spring Validator` (так как если мы просто в БД поставим UNIQUE, не будет выведена демонстрация пользователю в
  чем проблема. 
* Надо и **SQL UNIQUE** сделать и **Spring Validator** использовать для указания ошибки валидации пользователям

#### Приложение:
* Validator, @Override метод `supports()` это специальный метод не позволяет использовать наш Валидатор на любых других объектов кроме как на объектов класса Person
* Validator @Override метод `validate()`, **rejectValue имеет 3 поля:** 1. на каком поле произошла ошибка, 2. код ошибки пока не указываем, 3. сообщение ошибки)
* Для метода show() изменим на `Optional<Person>` объект обёртка вокруг тех объектов которые могут существовать а могут не существовать. Так как его теперь чаще используют вместо проверки на null