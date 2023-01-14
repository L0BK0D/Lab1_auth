# Lab1_auth

## Задание
- Спроектировать и разработать систему авторизации пользователей на протоколе HTTP.
## Ход работы
### Разработка пользовательского интерфейса и описание сценариев работы

#### Авторизация
Первое куда попадает пользователь, главная страница регистрации - `index.php`, где пользователь получает право выбора, войти существвующим аккаунтом или произвести регистрацию. В интерфейсе имеются несколько строк: "Логин, Пароль, Войти", а так же кнопку и  надпись `зарегистрируйтесь`. Если пользователь уже зарегестрированный аккаунт, то при правильном вводе логина и пароля его переакинет на страничку профиля - `profile.php`. В случае неправильного ввода данных пользователь увидит окно `Неверный логин или пароль` под формой авторизации. 
- Схема процесса авторизации

![autorization scheme](Лаб1/1.png "autorization scheme")

Если у пользователя нет аккаунта, он переходит на страничку регистрации `register.php` путём нажатия на гиперссылку в слове `зарегистрируйтесь`. Пользователя получвает форму регистрации, содержащая поля для данных и так-же, предлагается загрузить собственную картинку профиля. По мере заполнения формы, пользователь должен убедиться, что поля `Пароль` и `Подтверждение пароля` содержат одинаковое кол-во символов и они совпадают. В случае, если данные поля отличаются содержимым и пользователь нажимает `Войти`, под окном регистрации появится уведомление `Пароли не совпадают` и прийдётся заполнять все строки заново. В ином же случае, пользователя переадресует на страничку входа, и под формой авторизации будет уведомление `Регистрация прошла успешно`.
- Схема процесса регистрации 
- 
![registration scheme](Лаб1/2.png "registration scheme")

Если регистрация проходит успешно, пользователь получает доступ к сайту, под свои логином и паролем, которые ранее указывались при регистрации. После корректного ввода данных, пользователь окажется на странице `profile.php`, где будут отображены все данные, указанные при регистрации. Ниже будет надпись "Выход", нажав на которую, пользователь выйдет из аккаунта и перейдёт на страницу авторизации `index.php`.

### Структура Базы Данных
Данные зарегистрированых пользователей храняться в базе данных. База данных состоит из следующих полей : `id`, `full_name`, `login`, `email`, `password`, и `avatar`.
#### Содержимое полей Базы Данных
- `id` - Уникальный идентификатор пользователя
- `full_name` - ФИО пользователя
- `login` - Логин пользователя
- `email` - Email пользователя
- `password` - Захешированный пароль пользователя
- `avatar` - Ссылка на аватар пользователя
