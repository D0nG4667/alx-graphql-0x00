# Rick and Morty GraphQL App (GraphQuest Task 3)

This project is part of the GraphQuest learning journey. It sets up a Next.js application with TypeScript, ESLint, Tailwind CSS, and Apollo Client to consume the Rick and Morty GraphQL API.

## Objectives

- Initialize a Next.js project with TypeScript, ESLint, and Tailwind CSS.
- Configure Apollo Client to connect to the Rick and Morty GraphQL endpoint.
- Define GraphQL queries for episodes.
- Wrap the application with ApolloProvider for React integration.

## Setup Instructions

1. Create the project:

   ```bash
   npx create-next-app@latest alx-rick-and-morty-app --ts --eslint --tailwind
   cd alx-rick-and-morty-app
   ```

2. Install dependencies:

   ```bash
   npm install @apollo/client graphql
   npm install @types/graphql
   ```

3. Create a `graphql` directory in the project root.

4. Add `apolloClient.ts`:

   ```ts
   import { ApolloClient, InMemoryCache, HttpLink } from "@apollo/client";

   const client = new ApolloClient({
     link: new HttpLink({
       uri: "https://rickandmortyapi.com/graphql"
     }),
     cache: new InMemoryCache()
   });

   export default client;
   ```

5. Add `queries.ts`:

   ```ts
   import { gql } from "@apollo/client";

   export const GET_EPISODES = gql`
     query getEpisodes($page: Int, $filter: FilterEpisode) {
       episodes(page: $page, filter: $filter) {
         info {
           pages
           next
           prev
           count
         }
         results {
           id
           name
           air_date
           episode
         }
       }
     }
   `;
   ```

6. Update `pages/_app.tsx`:

   ```tsx
   import "@/styles/globals.css";
   import type { AppProps } from "next/app";
   import { ApolloProvider } from "@apollo/client";
   import client from "@/graphql/apolloClient";

   export default function App({ Component, pageProps }: AppProps) {
     return (
       <ApolloProvider client={client}>
         <Component {...pageProps} />
       </ApolloProvider>
     );
   }
   ```

7. Run the app:

   ```bash
   npm run dev
   ```

   Open [http://localhost:3000](http://localhost:3000) in your browser.

## Notes

- This task is mandatory and part of the GraphQuest learning journey.
- Future tasks will build on this setup to query and display characters and episodes.
