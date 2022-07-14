# Проект

## web-приложение "Отзывы на продукт"

**Технологии:**  

- Nodejs
- Express
- ejs
- MVC
- csv
- json
- re
- SQLite
- html
- css
- lodash  

Используется паттерн (шаблон построения архитектуры приложения) проектирования MVC.  

**MVC** - паттерн (Model-View-Controller)  

---  

**model** - модель - это часть архитектуры приложения:  

- включает в себя бизнес-логику приложения (классы, методы, функции обработки данных);  
- модель "не знает" о контроллерах и представлениях, не ориентируется на них;  
- данные модели могут быть представлены таблицами базы данных или файлами XML, JSON, csv;  
- это может быть просто набор объектов или функций для реализации логика приложения.  

---  

**view** - представление - это часть архитектуры приложения:

- отвечает за визуальное отображение данных, полученных от модели  
- представление может читать данные, но не может записывать или изменять их  
- представление может иметь программный код, который реализует логику отображения данных  

Примеры представления: HTML-страница, WPF форма, Windows Form.  

---  

**controller** - контроллер - это часть архитектуры приложения:  
- совокупность обработчиков событий представления  
- принимает события от представления  
- отдаёт событие на обработку в модель  
- возвращает пользователю обновлённое представление  
- или выбирает какое именно представление должно быть отображено в ответ  

---  

[Статья: MVC vs MVP vs MVVM](https://habr.com/ru/post/215605/)

---  

**Дерево директорий приложения:**  

![Дерево директорий приложения](readme/app_tree.png)

При наличии файла **package.json** можно установить сразу все необходимые зависимости так:  

```txt
npm i
```

Содержимое файла **package.json** при хранении данных в csv-файле (без БД SQLite):

```js
{
  "dependencies": {
    "csvjson": "^5.1.0",
    "ejs": "^3.1.6",
    "express": "^4.17.3"
  }
}
```

Либо каждую из зависимостей установить отдельно:  

```js
npm i csvjson
npm i ejs
npm i express
```

При использовании БД SQLite (вместо хранения данных в csv-файле) можно установить одну из этих библиотек:  

```js
npm i sqlite-sync
npm i sqlite3
```

Запуск приложения:  

```js
node app
```

После запуска можно в браузере увидеть главную форму приложения, перейдя по адресу:  

```txt
localhost:3000/
```

Главная форма приложения:  
![Главная форма приложения](readme/intro.png)  

Дочерняя форма приложения для отображения отзывов:  
![Дочерняя форма приложения](readme/feeds.png)  

Форма приложения для набора нового отзыва:  
![Дочерняя форма приложения](readme/new_feed.png)  

---  

### Задания для самостоятельного исполнения  

1) добавить поле "Оценка продукта" (добавить отдельный, самый правый столбец таблицы)  
- добавить в таблицу БД и в шаблон html-страницы с отзывами и в обработчик события  
- на шаблоне страницы по вводу отзыва добавить поле input типа number для ввода оценки и установить ограничения от 1 до 10 (10 - это высокая оценка)  
2) сделать вывод на страницу с отзывами отсортированным с обратном поряде по полю "Оценка продукта"  
- вверху таблицы отзывы с высокой оценкой, внизу - с низкой  
3) изменить на свой вкус дизайн меню, фона, кнопок, шрифтов, цветовое оформление...  
4) выбрать для себя тему работы - тот продукт (фирму, фильм, игру и т.д.), о котором будут отзывы  
- на стартовой странице поменять логотип и текст описания  
- заменить отзывы, которые были в БД с примерами работы на свои (согласно выбранной теме, ~ штук 10 отзывов)  

---  

Директории с примерами приложений:  

- 01-csv - реализация с хранением данных в csv-файле  
- 02-sqlite - реализация с хранением данных в БД SQLite (два разных подхода: синхронный и асинхронный доступ к данным)  
- ...  
- ...  

---  