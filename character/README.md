# Character Queries (GraphQuest Task 0)

This directory contains GraphQL queries to fetch specific characters by ID from the Rick and Morty GraphQL API.

## Endpoint

[https://rickandmortyapi.com/graphql](https://rickandmortyapi.com/graphql)

## Objective

Write GraphQL queries using the `character(id: ID!)` field to retrieve details of specific characters.

### Fields requested

- id
- name
- status
- species
- type
- gender

## Files

- `character-id-1.graphql` → Query for character with ID 1
- `character-id-1-output.json` → Output from API
- `character-id-2.graphql` → Query for character with ID 2
- `character-id-2-output.json` → Output from API
- `character-id-3.graphql` → Query for character with ID 3
- `character-id-3-output.json` → Output from API
- `character-id-4.graphql` → Query for character with ID 4
- `character-id-4-output.json` → Output from API

## Usage

Run queries against the Rick and Morty GraphQL endpoint using a GraphQL client (Apollo Studio Explorer, GraphiQL, or curl).

Example:

```graphql
query {
  character(id: 1) {
    id
    name
    status
    species
    type
    gender
  }
}
