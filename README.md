
---

# GraphQL Server with Express and MongoDB

This project sets up a GraphQL server using Apollo Server, Express, and MongoDB. It allows you to manage users and todos through a GraphQL API.

## Setup

1. **Clone the repository:**

    ```bash
    git clone <repository_url>
    cd graphql-express-mongodb
    ```

2. **Install dependencies:**

    ```bash
    npm install
    ```

3. **Set up MongoDB:**

    Make sure you have MongoDB installed and running locally. You can change the MongoDB connection URL in the `connectDB` function inside `server.js` if needed.

4. **Start the server:**

    ```bash
    npm start
    ```

    The GraphQL server will start running on `http://localhost:4000/graphql`.

## Usage

### Queries

- **Get a user by ID:**
  
    ```graphql
    query {
      getUserByID(userID: "user_id_here") {
        userID
        name
        email
      }
    }
    ```

- **Get all users:**

    ```graphql
    query {
      getUsers {
        userID
        name
        email
      }
    }
    ```

- **Get a todo by ID:**

    ```graphql
    query {
      getTodoByID(id: "todo_id_here") {
        userID
        id
        title
        completed
      }
    }
    ```

- **Get all todos:**

    ```graphql
    query {
      getTodos {
        userID
        id
        title
        completed
      }
    }
    ```

- **Get todos by user ID:**

    ```graphql
    query {
      todosByUserID(userID: "user_id_here") {
        userID
        id
        title
        completed
      }
    }
    ```

### Mutations

- **Create a user:**

    ```graphql
    mutation {
      createUser(userID: "user_id_here", name: "User Name", email: "user@example.com") {
        userID
        name
        email
      }
    }
    ```

- **Update a user:**

    ```graphql
    mutation {
      updateUser(userID: "user_id_here", name: "New Name", email: "new_email@example.com") {
        userID
        name
        email
      }
    }
    ```

- **Delete a user:**

    ```graphql
    mutation {
      deleteUser(userID: "user_id_here") {
        userID
        name
        email
      }
    }
    ```

- **Create a todo:**

    ```graphql
    mutation {
      createTodo(userID: "user_id_here", id: "todo_id_here", title: "Todo Title", completed: false) {
        userID
        id
        title
        completed
      }
    }
    ```

- **Update a todo:**

    ```graphql
    mutation {
      updateTodo(id: "todo_id_here", title: "Updated Title", completed: true) {
        userID
        id
        title
        completed
      }
    }
    ```

- **Delete a todo:**

    ```graphql
    mutation {
      deleteTodoByID(id: "todo_id_here") {
        userID
        id
        title
        completed
      }
    }
    ```

---

Feel free to customize the README according to your project's specific details and requirements.