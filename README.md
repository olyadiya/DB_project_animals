# Работа с датасетом: Animals in Children's Literature

Датасет: *Replication Data for: How Exactly does Literary Content Depend on Genre? A Case Study of Animals in Children's Literature*

В датасете собраны упоминания животных в произведениях детской литературы. Лингвистическая ценность датасета: позволяет исследовать, как менялся набор образов животных в детских текстах в зависимости от эпохи и автора.

``` mermaid
erDiagram
  authors {
    INT author_id
    VARCHAR author_name
  }
  documents {
    VARCHAR doc_id
    VARCHAR title
    INT year
    INT author_id FK
  }
  animals_dictionary {
    INT animal_id
    VARCHAR lemma
    JSON annotations
    VARCHAR animal_category
  }
  context {
    INT context_id
    VARCHAR doc_id
    INT animal_id
    JSON meta
  }
  authors ||--o{ documents : "пишет"
  documents ||--o{ context : "содержит"
  animals_dictionary ||--o{ context : "упоминается в"
```
