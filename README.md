В файле README.md написать запросы для MongoDB.
Каждый документ коллекции books должен содержать следующую структуру данных:

{
  title: "string",
  description: "string",
  authors: "string"
}

# 1. Запрос(ы) для вставки данных минимум о двух книгах в коллекцию books.

db.books.insertMany( [
    {
    title: "Совершенный код",
    description: "Книга посвящена структурированию программного кода",
    authors: "Макконнелл"
    },
    {
    title: "Простоквашино",
    description: "Хорошая книга для детей",
    authors: "Э. Успенский"
    },
    {
    title: "Война и мир",
    description: "Русская художественная литература",
    authors: "Л.Н. Толстой"
    }    
   ] )

# 2. Запрос для поиска полей документов коллекции books по полю title.
db.books.find(
    { "title": "Война и мир" }
)

# 3. Запрос для редактирования полей: description и authors коллекции books по _id записи.
db.books.updateOne(
    { _id: 1 },
    { $set:
        {
            description: "new description",
            authors: "new author"
        }
    }
)