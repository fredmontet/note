GraphQL
=======

Query with ApolloClient, the result is a promise.

  client.query({
    query: gql`
      query FeedQuery {
        feed {
          links {
            id
          }
        }
      }
    `
  }).then(response => console.log(response.data.allLinks))
