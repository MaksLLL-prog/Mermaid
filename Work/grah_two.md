```mermaid
graph TD
    %% Архитектура веб-приложения

    %% Frontend
    subgraph Frontend
        RE[React]
        RD[Redux]
        RT[Router]
    end

    %% Backend
    subgraph Backend
        N[Node.js]
        E[Express]
        M[MongoDB]
    end

    %% Внешние сервисы
    subgraph External
        S_Stripe[Stripe Payment]
        SG_SendGrid[SendGrid Email]
    end

    %% Связи
    RE --> RD
    RE --> RT
    RD --> N
    RT --> N
    N --> E
    E --> M
    N --> S_Stripe
    N --> SG_SendGrid

