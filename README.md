# sqlboiler-graphql-schema

We want developers to be able to build software faster using modern tools like GraphQL, Golang, React Native without depending on commercial providers like Firebase or AWS Amplify.

This program generates a grapql schema based on the generated sqlboiler structs we do this because we want to support the sqlboiler aliasing in our schema. Generating the schema is a good way too add type safety to queries and filters and prevent too much manual typing.

You can edit your schema like you want later and re-generate if your database changes. This program will create a merge conflict with your existing schema so you can choose to accept/reject changes.

## How to run

`go run github.com/aliChherawalla/sqlboiler-graphql-schema`

## Before running

- Install prettier globally (https://prettier.io/ `yarn global add prettier`)
- Install git command line (required to do three way merging)

## Options

```
NAME:
   sqlboiler-graphql-schema

USAGE:
   sqlboiler-graphql-schema [global options] command [command options] [arguments...]

COMMANDS:
   help, h  Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --input value              directory where the sqlboiler models are (default: "models")
   --output value             filepath for schema (default: "schema.graphql")
   --skip-input-fields value  input names which should be skipped: e.g. --skip-input-fields=userId --skip-input-fields=organizationId
   --mutations                generate mutations for models (default: true)
   --batch-update             generate batch update for models (default: true)
   --batch-create             generate batch create for models (default: true)
   --batch-delete             generate batch delete for models (default: true)
   --pagination               generate pagination support for models (default: "")
   --help, -h                 show help (default: false)
```


## Features
- [x] Support for manual updating the schema and re-generating (doing a three way merge https://github.com/charlesvdv/go-three-way-merge)
- [x] Generating basic models
- [x] Generating basic queries
- [x] Generating mutations (Followed best practices https://blog.apollographql.com/designing-graphql-mutations-e09de826ed97)
- [x] Generating filter for array queries (100%)
- [x] Generating filters for relationships (100%)
- [x] Generating input for mutations (100%)
- [x] Generating payload for mutations (100%)
- [x] Generating mutations (100%)
- [x] Generating mutations for array models (0% WIP)
- [x] Generating pagination for array models (20%, offset-based pagination done, TODO: cursor-based paginiation)

## Future roadmap

- [ ] Tests / snapshots
- [ ] Edges / connections
- [ ] Detecting when relationship is many to many
- [ ] Adding node from to many-to-many relationships
- [ ] Removing node from many-to-many relationships
- [ ] Supporting schema per model
