Create 5 different users: Jane Amsden, Emily Dixon, Theodore Dostoevsky, William Shapiro, Lao Xiu
INSERT INTO users (first_name, last_name) VALUES ("Jane", "Amsden"), ("Emily", "Dixon"), ("Theodore", "Dostoevsky"), ("William", "Shapiro"), ("Lao", "Xiu");


Create 5 books with the following names: C Sharp, Java, Python, PHP, Ruby
INSERT INTO books (title) VALUES ("C Sharp"), ("Java"), ("Python"), ("PHP"), ("Ruby");

INSERT INTO books (number_of_pages) VALUES (318), (297), (310), (288), (245);


Change the name of the C Sharp book to C#
UPDATE books SET title = "C#" WHERE title = "C Sharp";

Change the first name of the 4th user to Bill
UPDATE users SET first_name = "Bill" WHERE users.id = 4;

Have the first user favorite the first 2 books
Have the second user favorite the first 3 books
Have the third user favorite the first 4 books
Have the fourth user favorite all the books
INSERT INTO favorites (user_id, book_id) VALUES (1, 1), (1, 2), (2, 1), (2, 2), (2, 3), (3, 1), (3, 2), (3, 3), (3, 4), (4, 1), (4, 2), (4, 3), (4, 4), (4, 5);

Retrieve all the users who favorited the 3rd book
SELECT * FROM users LEFT JOIN favorites ON users.id = favorites.user_id LEFT JOIN books ON favorites.book_id = books.id WHERE books.id = 3;
SELECT * FROM users JOIN favorites ON users.id = favorites.user_id WHERE favorites.book_id = 3;

Remove the first user of the 3rd book's favorites
DELETE FROM favorites WHERE user_id = 2 AND book_id = 3;
DELETE FROM favorites WHERE user_id = (SELECT user_id FROM favorites WHERE book_id = 3 ORDER BY user_ID ASC LIMIT 1);

Have the 5th user favorite the 2nd book
INSERT INTO favorites (user_id, book_id) VALUES (5,2);

Find all the books that the 3rd user favorited
SELECT * FROM books JOIN favorites ON books.id = favorites.book_id WHERE favorites.user_id = 3;

Find all the users that favorited to the 5th book
SELECT * FROM users JOIN favorites ON users.id = favorites.user_id WHERE favorites.book_id = 5;
