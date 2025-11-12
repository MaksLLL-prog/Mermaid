```mermaid
sequenceDiagram
    title Процесс заказа такси

    participant C as Клиент
    participant A as Приложение
    participant S as Сервер
    participant D as Водитель

    C->>A: Вызывает такси
    activate A
    A->>S: Отправляет запрос на сервер
    activate S
    S->>S: Ищет свободного водителя
    S-->>D: Отправляет запрос водителю
    activate D
    D-->>S: Принимает заказ
    deactivate D
    S-->>C: Уведомляет клиента
    deactivate S
    A-->>C: Отображает данные водителя
    deactivate A
    D->>C: Забирает клиента
