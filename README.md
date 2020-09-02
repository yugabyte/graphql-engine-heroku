# Hasura GraphQL Engine on Heroku Powered by Yugabyte Cloud

[![GitHub stars](https://img.shields.io/github/stars/yugabyte/yugabyte-db.svg?style=social&label=Star)](https://github.com/yugabyte/yugabyte-db) 
<a href="https://twitter.com/intent/follow?screen_name=Yugabyte"><img src="https://img.shields.io/badge/Follow-Yugabyte-blue.svg?style=flat&logo=twitter"></a>

The Heroku add-on integrates Yugabyte Cloud seamlessly with Heroku, a popular developer PaaS. It allows developers to use YugabyteDB as the system-of-record database for any of their Heroku apps. Through the add-on, Heroku users can quickly have their YugabyteDB running on AWS and GCP (Azure coming soon!). Using it is just as easy as you expect from any PaaS: simply add the add-on dependency to your Heroku app, and you’re good to go!

Hasura GraphQL Engine is a blazing-fast GraphQL server that gives you :zap: **instant,
realtime GraphQL APIs over Yugabyte**, with [**webhook
triggers**](https://github.com/hasura/graphql-engine/blob/master/event-triggers.md)
on database events for asynchronous business logic.

Hasura helps you build GraphQL apps backed by YugabyteDB or incrementally move to
GraphQL for existing applications using Postgres. 

Deploy Hasura GraphQL Engine with Yugabyte Cloud and get a GraphQL endpoint in under 30 seconds :clock1:

Read more at [Hasura docs](https://docs.hasura.io) or [Yugabyte Cloud docs](https://docs.yugabyte.com/latest/yugabyte-cloud/free-tier/). 


## Quickstart

### 1. Deploy to Heroku 
Deploy to Heroku and instantly get a realtime GraphQL API backed by Yugabyte Cloud add-on:

[![Deploy to
Heroku](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/yugabyte/graphql-engine-heroku)

![Create New App - Heroku](https://graphql-engine-cdn.hasura.io/heroku-repo/assets/create_new_app_heroku_3.png)

### 2. Open Hasura Console

Once the deployment is complete, click on the `View` button as marked above.
This will take you to the Hasura Console, where you can create a table and make
your first GraphQL query. 

![Hasura Console](https://graphql-engine-cdn.hasura.io/heroku-repo/assets/hasura_console.png)

### 3. Create a table

Navigate to `Data -> Create table` on the console and create a table called
`profile` with the following columns:

| name   | type                     |
|--------|--------------------------|
| `id`   | Integer (auto-increment) |
| `name` | Text                     |

Choose `id` as the Primary key and click the `Create` button.

![Hasura Console - Create table](https://graphql-engine-cdn.hasura.io/heroku-repo/assets/hasura_create_table.png)

### 4. Insert sample data

Once the table is created, go to the `Insert Row` tab and insert some sample
rows:
```
Thor
Iron Man
Hulk
Captain America
Black Widow
```

![Hasura Console - Insert rows](https://graphql-engine-cdn.hasura.io/heroku-repo/assets/hasura_insert_row.png)

### 5. Try out GraphQL

Switch to the `GraphiQL` tab on top and execute the following GraphQL query:

```graphql
query {
  profile {
    id
    name
  }
}
```

![Hasura Console - GraphQL query](https://graphql-engine-cdn.hasura.io/heroku-repo/assets/hasura_graphql_query.png)

### 6. View your database console

Access your database console by going to your Heroku dashboard and clicking the add-on name.

![Yugabyte Cloud - Heroku add-on](https://blog.yugabyte.com/wp-content/uploads/2020/09/cloud-addon.png)

Then click "Go to cluster" to be redirected to the database console.

![Yugabyte Cloud - List Clusters](https://blog.yugabyte.com/wp-content/uploads/2020/09/cluster-list.png)

## Support & Troubleshooting

Feel free to talk to us on [Slack](https://www.yugabyte.com/slack) about anything
and everything. You can also contact us using one of the following channels: 

* Support & feedback: [Slack](https://www.yugabyte.com/slack)
* Issue & bug tracking: [GitHub issues](https://github.com/yugabyte/yugabyte-db/issues)
* Follow product updates: [@Yugabyte](https://twitter.com/yugabyte)
* Questions? [Forum](https://forum.yugabyte.com/)

## What's next

- Configuring [Yugabyte Cloud](https://devcenter.heroku.com/articles/yugabyte-cloud)
- Explore [YugabyteDB features](https://docs.yugabyte.com/latest/explore/)
- Install [YugabyteDB](https://docs.yugabyte.com/latest/quick-start/) on your local machine and try out [YSQL](https://docs.yugabyte.com/latest/api/postgresql/) from our docs
- [Contact](https://www.yugabyte.com/contact-us/) us to learn more about licensing, pricing or to schedule a technical overview

## Further reading

- [Using an existing Heroku database](https://docs.hasura.io/1.0/graphql/manual/deployment/heroku/using-existing-heroku-database.html)
- [Securing your GraphQL Endpoint](https://docs.hasura.io/1.0/graphql/manual/deployment/heroku/securing-graphql-endpoint.html)
- [Building your schema](https://docs.hasura.io/1.0/graphql/manual/schema/index.html)
- [GraphQL Queries](https://docs.hasura.io/1.0/graphql/manual/queries/index.html)
