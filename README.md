# Install

```shell
meteor add mpowaga:blaze-apollo
```

# Example

See an example [mpowaga/meteor-blaze-apollo-example](https://github.com/mpowaga/meteor-blaze-apollo-example).


# mpowaga:BlazeApollo
Blaze integration for the Apollo Client. Load GraphQL data directly in your templates!

## Installation

```
meteor add mpowaga:blaze-apollo
meteor npm install --save apollo-client
```

## Setup

```javascript
import ApolloClient from 'apollo-client';
import connect from 'meteor/mpowaga:blaze-apollo';
import { meteorClientConfig } from 'meteor/apollo';

const client = new ApolloClient(meteorClientConfig());

connect(client);
```

# WIP

## Something to query.

For the examples below we'll use the following data:

```javascript
Template.chat.queries({
  messagesQuery: {
    query: gql`
      query messages($channel: String!) {
        messages(channel: $channel) {
          username
          content
        }
      }
    `,
    variables: (instance) => ({
      channel: instance.channel.get()
    })
  }
});
```

## Basic template example

```handlebars
<!-- WIP -->
```

```javascript
import './wip.html';

Template.wip.helpers({
  wip() {
    return Template.messagesQuery().refetch();
  }
});
```

And done! GraphQL data in your templates!

Besides `query`, all other options for [ApolloClient.watchQuery](http://dev.apollodata.com/core/apollo-client-api.html#ApolloClient.watchQuery) can be declared in yourqueries object. Like `pollInterval`, `forceFetch`, `noFetch` and `variables`.
