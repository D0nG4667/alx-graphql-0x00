# Episode Queries (GraphQuest Task 2)

This directory contains GraphQL queries to fetch specific episodes by ID from the Rick and Morty GraphQL API.

## Endpoint

[https://rickandmortyapi.com/graphql](https://rickandmortyapi.com/graphql)

## Objective

Write GraphQL queries using the `episode(id: ID!)` field to retrieve details of specific episodes.

### Fields requested:

- id
- name
- air_date
- episode

## Files

- `episode-id-1.graphql` → Query for episode with ID 1
- `episode-id-1-output.json` → Output from API
- `episode-id-2.graphql` → Query for episode with ID 2
- `episode-id-2-output.json` → Output from API
- `episode-id-3.graphql` → Query for episode with ID 3
- `episode-id-3-output.json` → Output from API
- `episode-id-4.graphql` → Query for episode with ID 4
- `episode-id-4-output.json` → Output from API

## Usage

Run queries against the Rick and Morty GraphQL endpoint using a GraphQL client (Apollo Studio Explorer, GraphiQL, or curl).

Example:

```graphql
query {
  episode(id: 1) {
    id
    name
    air_date
    episode
  }
}
