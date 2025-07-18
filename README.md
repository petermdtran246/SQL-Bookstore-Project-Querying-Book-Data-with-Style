
# 📘 Bookstore SQL Queries

## 📝 Problem Statement / Prompt

You're working with a fictional bookstore database. The database contains one main table called `books`, with various information about book titles, authors, release years, stock, and page counts.

Your tasks:
- Write SQL queries that demonstrate data manipulation and string functions.
- Simulate real-world queries like reversing strings, formatting author names, counting characters, and shortening titles for UI display.
- Showcase creative data transformation using SQL built-in functions.

---

## 📂 File: `book_data.sql`

This file includes:
- Table creation for `books`
- Preloaded sample data for 16 books with varying metadata

---

## ✅ SQL Tasks & Queries Covered

1. **Reverse and Uppercase a sentence**
```sql
SELECT REVERSE(UPPER('Why does my cat look at me with such hatred?'));
```

2. **String manipulation using `REPLACE` and `CONCAT`**
```sql
SELECT REPLACE(CONCAT('I', ' ', 'like', ' ', 'cats'), ' ', '_');
```

3. **Replace all spaces in book titles**
```sql
SELECT REPLACE(title, ' ', '->') AS title FROM books;
```

4. **Author name reversal**
```sql
SELECT author_lname AS forward, REVERSE(author_lname) AS backward FROM books;
```

5. **Uppercase full name**
```sql
SELECT UPPER(CONCAT(author_fname, ' ', author_lname)) AS 'full name in caps' FROM books;
```

6. **Book title blurbs**
```sql
SELECT CONCAT(title, ' was released ', released_year) AS blurb FROM books;
```

7. **Length of each book title**
```sql
SELECT title, CHAR_LENGTH(title) AS 'character count' FROM books;
```

8. **Shortened title + author + quantity string**
```sql
SELECT 
  CONCAT(SUBSTR(title, 1, 10), '...') AS 'short title',
  CONCAT(author_lname, ', ', author_fname) AS author,
  CONCAT(stock_quantity, ' in stock') AS quantity
FROM books 
LIMIT 10;
```

---

## 📌 How to Run

1. Start your MySQL server and open terminal.
2. Create the database `book_shop`:
```sql
CREATE DATABASE book_shop;
USE book_shop;
```
3. Import data:
```bash
mysql -u root -p book_shop < book_data.sql
```
4. Run any of the SQL queries above.

---

## 💡 Highlights

- Demonstrates real-world usage of string functions like `CONCAT`, `REPLACE`, `REVERSE`, `UPPER`, `CHAR_LENGTH`, and `SUBSTR`.
- Cleanly structured dataset with books by well-known authors.
- Practical query examples great for showcasing SQL fluency.
