```mermaid
erDiagram
    USERS {
        int id PK
        string name
        string email
    }

    ORDERS {
        int id PK
        int user_id FK
        int restaurant_id FK
        boolean isPaid
        string status
    }

    ITEMS {
        int id PK
        string name
        float price
        int restaurant_id FK
    }

    ORDER_ITEMS {
        int order_id FK
        int item_id FK
        int quantity
    }

    RESTAURANTS {
        int id PK
        string name
    }

    COURIERS {
        int id PK
        string name
    }

    %% Связи
    USERS ||--o{ ORDERS : делает
    RESTAURANTS ||--o{ ORDERS : принимает
    ORDERS ||--o{ ORDER_ITEMS : содержит
    ITEMS ||--o{ ORDER_ITEMS : входит
    RESTAURANTS ||--o{ ITEMS : предлагает
    COURIERS ||--o{ ORDERS : доставляет
