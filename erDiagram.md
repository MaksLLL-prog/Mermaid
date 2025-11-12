```mermaid
erDiagram
    %% Таблицы
    USERS {
        int id PK
        string name
        string email
    }

    POSTS {
        int id PK
        string content
        int author_id FK
    }

    COMMENTS {
        int id PK
        string content
        int post_id FK
        int author_id FK
    }

    LIKES {
        int user_id FK
        int post_id FK
    }

    SUBSCRIPTIONS {
        int subscriber_id FK
        int subscribed_to_id FK
    }

    %% Связи
    USERS ||--o{ POSTS : "создает"
    USERS ||--o{ COMMENTS : "пишет"
    POSTS ||--o{ COMMENTS : "имеет"
    USERS ||--o{ LIKES : "ставит"
    POSTS ||--o{ LIKES : "получает"
    USERS ||--o{ SUBSCRIPTIONS : "подписан на"
    USERS ||--o{ SUBSCRIPTIONS : "имеет подписчиков"
