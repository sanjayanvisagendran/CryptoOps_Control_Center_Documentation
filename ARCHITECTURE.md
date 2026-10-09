# Architecture

```mermaid
flowchart TD
    A[Coinbase public order book] --> C[Collection service]
    B[Bitcoin mempool API] --> C
    C --> D[Control and risk engine]
    D --> E[(SQLite operations store)]
    E --> F[FastAPI service]
    F --> G[Streamlit dashboard]
    D --> H[Incident queue and audit log]
```

The project deliberately separates providers, calculations, controls, persistence and presentation so each part can be tested or replaced independently. Public read-only data is used; the system has no exchange credentials and cannot place trades or move funds.

