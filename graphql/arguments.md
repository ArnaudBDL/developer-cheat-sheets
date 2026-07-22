# GraphQL : Arguments

```graphql
type Query {
  article(id: ID!): Article
  articles(status: ArticleStatus, limit: Int = 20): [Article!]!
}
```

```graphql
query PublishedArticles {
  articles(status: PUBLISHED, limit: 10) {
    id
    title
  }
}
```

- Define precise types and sensible defaults.
- Validate ranges, formats and business rules.
- Prefer an input object when an operation needs several related values.
- Do not use arguments to bypass field or object authorization.
- Apply limits to list arguments and expensive filters.
