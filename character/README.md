# Character Queries (GraphQuest Tasks)

This directory contains GraphQL queries to fetch characters from the Rick and Morty GraphQL API.

## Endpoint

[https://rickandmortyapi.com/graphql](https://rickandmortyapi.com/graphql)

---

## Task 0: Specific Character by ID

- Queries: `character-id-1.graphql` → `character-id-4.graphql`
- Outputs: `character-id-1-output.json` → `character-id-4-output.json`
- Fields: id, name, status, species, type, gender

---

## Task 1: Paginated List of Characters

- Queries: `characters-page-1.graphql` → `characters-page-4.graphql`
- Outputs: `characters-page-1-output.json` → `characters-page-4-output.json`
- Fields: id, name, status, image

### Example Query

```graphql
query {
  characters(page: 1) {
    results {
      id
      name
      status
      image
    }
  }
}
