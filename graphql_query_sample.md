
[Github repo](https://github.com/byrmylmz/booksql-laravel/blob/ea44f377d7ba05a84566a9d3d611b980c3773331/graphql/schema.graphql#L7-L17)

### Laravel Graphql Server Highlights
- End Point Sample `http://project-name.test/graphql`
- Sample >[Schema.graphql](https://github.com/byrmylmz/booksql-laravel/blob/674780e10950e95fde559053cc55c1a11a67c543/graphql/schema.graphql) Including Books Project
- Sample Complex Query [SomeComplexQuery.php](https://github.com/byrmylmz/booksql-laravel/blob/674780e10950e95fde559053cc55c1a11a67c543/app/GraphQL/Queries/SomeComplexQuery.php)


```graphql
type Query {
    users: [User!]! @paginate(defaultCount: 10)
    user(id: ID @eq): User @find


    books:[Book] @all
    book(id: ID @eq): Book @find
    booksByFeatured(featured: Boolean! @eq): [Book] @all
    someComplexQuery(search: String!) [Book]


    categories:[Category] @all
    category(id: ID @eq): Category @find
   ```
   
# Create 
```graphql
mutation{
  createCategory(
    name:"deneme"
  ) {
    name
  }
}
```
# Update
```graphql
mutation{
  updateCategory(id:1, name:"new"){
    id
    name
  }
}
```
# query get data
```graphql
query{
  books{
    id
  }
}
```

# query with boolean
```graphql
// server
query($featured: Boolean!) {
  booksByFeatured(featured: $featured) {
    id
    title
    author
    image
  }
}
//client graphql
query{
  booksByFeatured(featured:true){
    id
    title
    
  }
}
```
   
   
