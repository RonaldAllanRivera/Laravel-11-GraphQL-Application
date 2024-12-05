install Lighthouse in your project.
#Install via composer
composer require nuwave/lighthouse


Install GraphQL DevTools
To make use of the amazing tooling around GraphQL, install GraphiQL
composer require mll-lab/laravel-graphiql
- visit http://127.0.0.1:8000/graphiql for testing, this app is similar to Postman


Querying fields in GraphQL, type:
{
    users {
        id
        name
        email
    }
}

Querying with arguments, type:
{
  user(id: 2){
    id
    name
    email
  }
}

Querying with aliases, type:
{
  userOne: user(id: 2){
    id
    name
    email
  }

  userTwo: user(id: 2){
    id
    name
    email
  }
}

Using the Lighthouse paginate directive, type
{
    users (first: 2, page: 1) {
        data 
        {
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

