Create 5 different users: Jane Amsden, Emily Dixon, Theodore Dostoevsky, William Shapiro, Lao Xiu
INSERT INTO users (first_name, last_name) VALUES ("Jane", "Amsden"), ("Emily", "Dixon"), ("Theodore", "Dostoevsky"), ("William", "Shapiro"), ("Lao", "Xiu");


Create 5 books with the following names: C Sharp, Java, Python, PHP, Ruby
INSERT INTO books (title) VALUES ("C Sharp"), ("Java"), ("Python"), ("PHP"), ("Ruby");

INSERT INTO books (number_of_pages) VALUES (318), (297), (310), (288), (245);


Change the name of the C Sharp book to C#
UPDATE books SET title = "C#" WHERE title = "C Sharp";

Change the first name of the 4th user to Bill
UPDATE users SET first_name = "Bill" WHERE users.id = 4;
