---

# Simple Search Engine with C++ HTTP Server

This project implements a basic **search engine** using **C++** with a simple **HTTP server**. The search engine indexes web pages and allows users to perform searches for specific content. The server handles search requests and returns results in the form of URLs where the content is found.

## Features

- Simple **HTTP server** built with **C++ sockets**.
- In-memory **inverted index** for efficient search.
- Ability to add **web pages** with content and perform searches based on tokens (words).
- Basic **web frontend** that allows users to submit search queries via a simple HTML form.
- **Search results** displayed as URLs of pages containing the searched tokens.

## Technologies Used

- **C++**: Core programming language.
- **Sockets**: For creating the HTTP server.
- **HTML**: Frontend to allow users to enter search queries.

## How to Run the Server

### 1. Clone the Repository

```bash
git clone https://github.com/kanyutu707/WebSearchEngine.git
cd WebSearchEngine
```

### 2. Compile the Code

To compile the code, run the following command:

```bash
g++ -o search_server main.cpp -pthread
```

This will compile the C++ code and generate an executable named `search_server`.

### 3. Run the Server

Run the server with:

```bash
./search_server
```

The server will start on **port 8080**.

### 4. Access the Web Frontend

Open your browser and go to:

```
http://localhost:8080
```

You should see the homepage with a search form.

### 5. Test the Search Engine

- Enter a search query in the text box and hit **Search**.
- If the query matches any pages, their URLs will be displayed as the result.
- If no results are found, the message "No results found." will be displayed.

### 6. Modify the Pages

You can add more pages to the search engine by modifying the `main()` function in the `search_server.cpp` file. Add `engine.addPage(WebPage(url, content));` with your desired page URLs and content.

## Code Explanation

### **Search Engine Components:**

- **WebPage Class**: Represents a web page with a `url` and `content`.
- **InvertedIndex Class**: Implements an inverted index, which maps words (tokens) to page IDs that contain those words.
- **SearchEngine Class**: Manages the collection of web pages and performs searches using the inverted index.

### **HTTP Server:**

- **Server Setup**: A simple HTTP server is created using **C++ sockets**. It listens on port `8080` and handles incoming GET requests.
- **Search Handling**: When a user submits a query, the server performs a search using the `search()` method of the `SearchEngine` class and returns the search results.
- **Frontend**: A simple HTML form allows users to enter a search query. The results are shown as clickable URLs that match the search query.

## Example Use Case

- Add pages to the search engine (for example, `https://example.com` with the content `"Example content with data structures and algorithms"`).
- The user enters a search query like "algorithms".
- The server searches for pages containing the word "algorithms" and returns a list of matching URLs.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
