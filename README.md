# 📚 Library Management API

A simple **Library Management API** built using [Gin](https://github.com/gin-gonic/gin), a lightweight and high-performance web framework for Go. This API allows users to manage a collection of books, including retrieving book details, adding new books, checking out books, and returning books.

---

## 🚀 Features

### 📖 Manage Books
- Retrieve a list of all books.
- Fetch details of a specific book by its unique ID.
- Add new books to the collection.

### 🔄 Book Transactions
- Check out a book (if available in stock).
- Return a borrowed book.

---

## 📂 API Endpoints

### 1️⃣ Get All Books
**`GET /books`**  
**Description**: Fetches a list of all available books in the library.  
**Response Example**:
```json
[
  { "id": "1", "title": "In Search of Lost Time", "author": "Marcel Proust", "quantity": 2 },
  { "id": "2", "title": "The Great Gatsby", "author": "F. Scott Fitzgerald", "quantity": 5 }
]
###2️⃣ Get Book by ID
GET /book/:id
Description: Retrieves a book's details using its unique ID.
Response Example (Success):

json
{ "id": "1", "title": "In Search of Lost Time", "author": "Marcel Proust", "quantity": 2 }
Response Example (Error):

json
{ "message": "Book not found." }
3️⃣ Add a New Book
POST /books
Description: Adds a new book to the library.
Request Body Example:

json
{
  "id": "4",
  "title": "1984",
  "author": "George Orwell",
  "quantity": 3
}
Response Example:

json
{ "id": "4", "title": "1984", "author": "George Orwell", "quantity": 3 }
4️⃣ Check Out a Book
PATCH /checkout?id={book_id}
Description: Reduces the quantity of the book by 1 if it is in stock.
Response Example (Success):

json

{ "id": "2", "title": "The Great Gatsby", "author": "F. Scott Fitzgerald", "quantity": 4 }
Response Example (Out of Stock):

json
Copy code
{ "message": "Book not available" }
5️⃣ Return a Book
PATCH /return?id={book_id}
Description: Increases the quantity of the book by 1.
Response Example:

json

{ "id": "2", "title": "The Great Gatsby", "author": "F. Scott Fitzgerald", "quantity": 5 }
🛠️ How to Run
Clone the repository:

bash

git clone <repository-url>
cd <repository-folder>
Install dependencies:

bash

go mod tidy
Run the application:

bash

go run main.go
Access the API:
The API will be available at:
http://localhost:8004

📝 Example Book Data
The API is initialized with the following book data:


[
  { "id": "1", "title": "In Search of Lost Time", "author": "Marcel Proust", "quantity": 2 },
  { "id": "2", "title": "The Great Gatsby", "author": "F. Scott Fitzgerald", "quantity": 5 },
  { "id": "3", "title": "War and Peace", "author": "Leo Tolstoy", "quantity": 6 }
]
📌 Requirements
Go 1.18 or later
Gin framework


