                                   2.1 «Теория хранения данных. Реляционная модель данных»‎
                            Задание: Разработать логическую структуру БД для создания "Библиотеки".

Сущности:
- читатели (readers)
- книги (books), причем каждая строка данной таблицы соответствует сразу всем экземплярам конкретной книги. Можно было ввести отдельную сущность - отдельный экземпляр книги - но с практической точки зрения это не нужно.
- автор(ы) (author)
- издательства (publishing)
- абонемент (lending_library).
Чтоб читатели и книги были связаны создана таблица абонемент в которой связан читатель и книги которые он читает. Автор тоже вынесены в отдельную сущность, так как у книги может быть множество авторов
Связи и ключи
В данной БД можно выделить 3 связи:

Связь «one to many» publishing - books. У книги может быть только одно издательство, у издательства множество книг. Первичный ключ (publishing) соответствует внешнему ключу books.publisher.
Связь «many to many» books - authors. У книги может быть больше одного автора, а у автора - множетсво книг. Вспомогательная таблица books_of_authors с двумя внешними ключами, соответствующими первичным ключам в таблицах books и authors используется для создания связи между ними.
Связь «many to many»  books-readers. Для реализации данной связи используется дополнительная таблица lending_library с двумя внешними ключами, которые соответсвуют первичным ключам в таблицах books и readers.  В таблице lending_library  можно выделить в отдельную сущность со своими собственными атрибутами, такими как дата выдачи и дата возврата. 
