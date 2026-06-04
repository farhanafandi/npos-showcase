# NPOS System Architecture

```mermaid
flowchart TD
    POS[Mobile POS App<br/>Flutter]
    CONSOLE[Admin Console<br/>React + TypeScript]
    
    API[Backend API<br/>Node.js + Express]
    DB[(MySQL Database)]
    
    AUTH[Authentication & Authorization]
    SALES[Sales Domain]
    INV[Inventory Domain]
    FIN[Finance Domain]
    HR[HR Domain]
    ASSET[Asset Domain]
    REPORT[Reporting Module]
    PRINT[Local Printer Service]

    POS --> API
    CONSOLE --> API

    API --> AUTH
    API --> SALES
    API --> INV
    API --> FIN
    API --> HR
    API --> ASSET
    API --> REPORT
    API --> PRINT

    AUTH --> DB
    SALES --> DB
    INV --> DB
    FIN --> DB
    HR --> DB
    ASSET --> DB
    REPORT --> DB