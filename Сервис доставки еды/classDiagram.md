```mermaid
classDiagram
    class User {
        +String name
        +Integer userId
        +List~Order~ orders
    }

    class Order {
        +Integer orderId
        +List~Item~ items
        +Boolean isPaid
        +String status
    }

    class Item {
        +String name
        +Float price
    }

    class Restaurant {
        +String name
        +List~Item~ menu
        +List~Order~ orders
    }

    class Courier {
        +String name
        +List~Order~ deliveries
    }

    %% Отношения
    User *-- Order : делает
    Order o-- Item : содержит
    Restaurant o-- Item : предлагает
    Restaurant o-- Order : принимает
    Courier *-- Order : доставляет
