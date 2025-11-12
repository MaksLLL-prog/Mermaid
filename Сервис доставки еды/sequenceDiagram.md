```mermaid
sequenceDiagram
    title Процесс заказа еды

    participant Client
    participant App
    participant Restaurant
    participant Courier

    Client->>App: Выбирает блюда и оформляет заказ
    activate App
    App->>Restaurant: Отправка заказа
    activate Restaurant
    Restaurant-->>App: Подтверждение готовности
    deactivate Restaurant
    App-->>Client: Уведомление о готовности
    deactivate App
    Restaurant->>Courier: Передача заказа
    activate Courier
    Courier->>Client: Доставка заказа
    deactivate Courier
