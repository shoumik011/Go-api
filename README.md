# Library Management API

This project is a simple **Library Management API** built with [Gin](https://github.com/gin-gonic/gin), a lightweight and high-performance web framework for Go. The API allows users to manage a collection of books, including retrieving book details, adding new books, checking out books, and returning books.

## Features

1. **Retrieve All Books**  
   Endpoint: `GET /books`  
   - Fetches a list of all books in the library.

2. **Retrieve Book by ID**  
   Endpoint: `GET /book/:id`  
   - Fetches the details of a specific book by its ID.  
   - Returns an error if the book is not found.

3. **Add a New Book**  
   Endpoint: `POST /books`  
   - Allows the addition of a new book to the library collection.  
   - Expects a JSON payload with book details (`id`, `title`, `author`, `quantity`).

4. **Check Out a Book**  
   Endpoint: `PATCH /checkout?id={book_id}`  
   - Reduces the quantity of a specified book by 1 if it is available.  
   - Returns an error if the book is not found or out of stock.

5. **Return a Book**  
   Endpoint: `PATCH /return?id={book_id}`  
   - Increases the quantity of a specified book by 1.  
   - Returns an error if the book is not found.

## How to Run

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>

