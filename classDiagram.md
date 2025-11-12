```mermaid
classDiagram
    %% Diagram of Library System

    class Book {
        +String title
        +String author
        +String ISBN
        +Boolean isAvailable
    }

    class User {
        +String name
        +Integer userId
        +List~Book~ borrowedBooks
    }

    class Library {
        +List~Book~ books
        +List~User~ users
    }

    %% Relationships
    User *-- Book : borrows
    Library o-- Book : contains
    Library o-- User : manages
