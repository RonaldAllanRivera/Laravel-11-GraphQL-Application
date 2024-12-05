# Laravel 11 GraphQL Application

A Laravel 11 project with default user GraphQL queries using **Lighthouse** for GraphQL support. This setup allows you to create, query, update, and delete users via GraphQL endpoints.

---

## Installation

Follow these steps to set up the project:

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/your-repository.git
cd your-repository


### 2. Install Backend Dependencies
```bash
composer install
```

### 3. Install Frontend Dependencies (Optional)
```bash
npm install
npm run dev
```

### 4. Set Up Environment
- Copy `.env.example` to `.env`:
  ```bash
  cp .env.example .env
  ```
- Update `.env` with your database and environment configurations.

### 5. Generate Application Key
```bash
php artisan key:generate
```

### 6. Run Migrations
```bash
php artisan migrate
```

### 7. Seed the Database (Optional)
```bash
php artisan db:seed
```

---

## Running the Application

### 1. Set the API Base URL
Update the `APP_URL` in your `.env` file:
```env
APP_URL=http://localhost:8000
```

### 2. Start the Application
```bash
php artisan serve
```

### 3. Access the API
Visit `http://localhost:8000/api` for your API routes.

---

## GraphQL Setup

### 1. Install Lighthouse
Lighthouse provides GraphQL support for Laravel:
```bash
composer require nuwave/lighthouse
```

### 2. Install GraphQL DevTools
To test GraphQL queries, install **GraphiQL**:
```bash
composer require mll-lab/laravel-graphiql
```
- Visit `http://127.0.0.1:8000/graphiql` to test your queries, similar to **Postman** for REST APIs.

---

## GraphQL Examples

### Query All Users
```graphql
{
    users {
        id
        name
        email
    }
}
```

### Query User by ID
```graphql
{
  user(id: 2) {
    id
    name
    email
  }
}
```

### Query with Aliases
```graphql
{
  userOne: user(id: 2) {
    id
    name
    email
  }
  userTwo: user(id: 3) {
    id
    name
    email
  }
}
```

### Paginate Users
```graphql
{
    users(first: 2, page: 1) {
        data {
            id
            name
            email
        }
        paginatorInfo {
            currentPage
            lastPage
            hasMorePages
            lastItem
            total
        }
    }
}
```

---

## GraphQL Mutations

### Create a User
```graphql
mutation {
    createUser(
        name: "Allan",
        email: "allan@domaintest.com",
        password: "passwordpassword"
    ) {
        id
        name
    }
}
```

### Update a User
```graphql
mutation {
    updateUser(
        id: 12,
        name: "Ronald"
    ) {
        id
        name
        email
    }
}
```

### Delete a User
```graphql
mutation {
    deleteUser(id: 12) {
        id        
    }
}
```

---

