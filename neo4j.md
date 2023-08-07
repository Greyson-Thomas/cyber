

[Reference Video](https://www.youtube.com/watch?v=oRtVdXvtD3o)
# Neo4J
## Intro to Graphs
- More ergonomic and synonymous with how our brain conceptualizes things
- Structure
  - Node: represents the object in the graph - Entities and complex value types
    - More similar to rows in a table
  - Relationship: relate nodes by type and direction - Connect entities and structure domain
  - Properties: Key-Value pairs that go with nodes and relationships - Entity attributes, relationshiop qualities, metadata
  - Label: Group nodes by role 
    - Similar to Entities in and ERD
    - Optimized and Indexed

## Neo4JGraph Database
- Strong ACID transactions
- Fast 
- Schemafree
- No Foreign Key
- Written in java
- Can specify the number of relationship hops you'd like in your query
- Joins are computed on creation instead of on query

### Graph Querying (Declarative)
- Cypher: a pattern matching query language for graphs
  - Properties of Cypher
    - Declarative
    - Expressive
    - Pattern Matching
      - ()-[]-() 
      - ()-[]->()
      - ()<-[]-()
  - Cypher Syntax
    - (variable:label) Label Syntax
    - {key:value} Property Syntax
    - -[:value]-> Relationship Syntax
  - Query Examples:
    - MATCH (p:Person)-[r:Acted_IN]->(m:Moveie) RETURN p,r,m
      - MATCH and RETURN are Cypher Keywords
      - :MOVIE is a node label
      - :Acted_IN is a relationship
    - MATCH (m:movie{title: 'Mystic River'}) SET m.tagline = 'text goes here' RETURN m
      - sets the tagline of the movie Mystic River to the provided text
    - MATCH (m:Movie{title: 'Title'}) MATCH (p:Person{name:'Provided Name'}) CREATE (p)-[r:ACTED_IN {roles: ['Sean']}]->(m) RETURN p,r,m
      - creates a relationship between 2 nodes
  - Aggregates: grouping key does not need to be specified
    - Auto groupby non-aggregate keys
  - Constraints and Index
    - Unique Constraint: ensure uniqueness - 
      - CREATE CONSTRAINT ON (label: Label) ASSERT label.property IS UNIQUE
      - Not globally unique - bound ot label
      - Types of Unique Constraints
        - Uniquie Node Property Constraint
        - Node Property Existence Constraint
        - Relationship Property Existence Constraint
    - Index: allow fast lookup of nodes that match by properties
      - Only used for finding the starting points
      - Index Free Adjacency: 
    - Merge Clause = create if not exist
      - Merge checks everything you give it. They must all be in existence if not then create the node
      - Should merge only on the key values and set anything else

## Learning Resources
- Neo4j Bloom: Graph Exploratory Visualizations
- [Neo4j-Documentation](https://neo4j.com/docs/)
- [Cypher-Documentation](https://neo4j.com/docs/cypher-manual/current/introduction/)
  - [Cypher-CheatSheet](https://neo4j.com/docs/cypher-cheat-sheet/5/auradb-enterprise/)
- [DataScience-Documentation](https://neo4j.com/docs/graph-data-science/current/introduction/)