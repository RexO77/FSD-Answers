
### **Module 1**

#### **Q1(a) - Define Web Framework. Explain with an example of the design of a Web application written using the Common Gateway Interface (CGI) standard with its disadvantages.** (10 marks)

**Answer:**

- **Web Framework**:
  - A web framework is a collection of tools, libraries, and conventions that simplifies the development of web applications. It provides reusable code and components, allowing developers to focus on the application logic rather than repetitive tasks such as routing, database connections, or session management.
  - Web frameworks often include features like URL routing, input validation, templating engines, and authentication modules, among others.

- **Common Gateway Interface (CGI)**:
  - **Definition**: CGI is an early standard for external applications to interact with web servers to generate dynamic content. It enables the server to execute programs, known as CGI scripts, to process user requests and return the result.
  - **How it Works**:
    1. A user makes an HTTP request to a web server.
    2. The server identifies the request as one requiring a CGI script.
    3. The server executes the CGI script, passing the user’s input data to the script via environment variables.
    4. The CGI script processes the data, interacts with the database or other resources if needed, and generates an output, usually in HTML format.
    5. The server then sends the script’s output back to the client as an HTTP response.

- **Example**:
  - Suppose we are building a simple web application for a library where users can search for books. The CGI script could be written in a language like Perl or Python.
  - **Steps**:
    1. The user enters a search query into an HTML form.
    2. The form sends the query to a CGI script on the server.
    3. The CGI script receives the query, searches the database for matching books, and formats the results as HTML.
    4. The server returns this HTML page to the user’s browser, displaying the search results.

- **Disadvantages of CGI**:
  1. **Performance Overhead**: Each time a request is made, the server spawns a new process to run the CGI script. This process creation is resource-intensive and leads to significant performance overhead, especially under high traffic.
  2. **Lack of Scalability**: Due to the overhead of creating a new process for each request, CGI does not scale well. If multiple users make requests simultaneously, the server could become overwhelmed.
  3. **Security Issues**: CGI scripts often deal with user input, which can be a vector for attacks if not properly sanitized. Poorly written CGI scripts can lead to vulnerabilities like command injection.
  4. **Difficulty in Maintenance**: CGI scripts are typically written in general-purpose programming languages, which means there is no standardized structure or framework. This lack of structure can make CGI scripts hard to maintain and debug as the application grows.

---

#### **Q1(b) - What is the Model-View-Controller (MVC) architecture? Explain its components with a suitable example.** (10 marks)

**Answer:**

- **Model-View-Controller (MVC) Architecture**:
  - MVC is a software architectural pattern commonly used for developing user interfaces that separates an application into three interconnected components: Model, View, and Controller.
  - The MVC pattern helps in organizing code in a way that separates concerns, making applications easier to manage, maintain, and test.

- **Components of MVC**:
  1. **Model**:
     - The Model represents the application's data and the business rules or logic that governs access and modification of this data.
     - It is responsible for managing the data, processing user inputs, and notifying the View of any changes to the data.
     - Example: In a blog application, the Model might include classes that represent blog posts, comments, users, and the logic for saving and retrieving these objects from a database.

  2. **View**:
     - The View is the presentation layer, which displays the data provided by the Model to the user. It is concerned with the visual representation of the Model's data.
     - The View listens for changes in the Model and updates the user interface accordingly.
     - Example: In the same blog application, the View could be the HTML pages that display a list of blog posts, a single blog post with comments, or a form for submitting a new post.

  3. **Controller**:
     - The Controller acts as an intermediary between the Model and the View. It receives user input from the View, processes it (often by making calls to the Model), and returns the output display to the View.
     - The Controller handles user actions like clicking a button, submitting a form, or any other interaction.
     - Example: In the blog application, the Controller might handle requests like creating a new blog post or editing an existing one. It would take the user's input, pass it to the Model to create or update the post, and then decide which View should be updated or rendered.

- **Example of MVC in a Web Application**:
  - **Scenario**: A simple e-commerce application where users can browse products, add them to a cart, and proceed to checkout.
  - **Model**: Classes representing Products, Carts, and Orders, along with methods to add products to the cart, calculate the total price, and process orders.
  - **View**: HTML pages that display the list of products, the cart contents, and the checkout form.
  - **Controller**: Handles requests such as adding a product to the cart, removing a product from the cart, or submitting the order at checkout. It interacts with the Model to update the cart's contents and passes the updated data to the View to be displayed to the user.
