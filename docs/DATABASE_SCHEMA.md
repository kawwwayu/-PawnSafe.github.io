```plaintext
+--------------------+                +--------------------+                +--------------------+
|      Profiles      |                |      Products      |                |     Favorites      |
+--------------------+                +--------------------+                +--------------------+
| id (PK)            |<-------------+ | id (PK)           |<-------------+ | id (PK)           |
| user_id (UK)       | 1            | | name              |              | | user_id (FK)      |
| name               |               | | description       |              | | product_id (FK)   |
| age                |               | | image_url         |              | +--------------------+
| bio                |               | | price             |
+--------------------+               N | rating            |
                                        | category          |
                                        | in_stock          |
                                        | user_id (FK)      |
                                        +--------------------+

Relationships:
- Profiles ↔ Products: A One-to-Many relationship, where one profile can be linked to multiple products.
- Profiles ↔ Favorites: A Many-to-Many relationship, where multiple profiles can add the same product to favorites.
```

