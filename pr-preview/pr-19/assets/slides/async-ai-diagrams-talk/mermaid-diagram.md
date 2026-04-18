# AI Diagram Flow v1

```mermaid
flowchart TD
    A[Drawing]
    B[Dodgy Diagram]
    C[Text-based Documentation]

    D[AI Coding Tool]
    E[Mermaid Diagram]
    F{Issues with diagram?}

    G[We're Done 🥳]
    H[Import Excalidraw]
    I[Edit]
    J[Export to repo]

    A --> D
    B --> D
    C --> D

    D --> E
    E --> F

    F -->|No| G
    F -->|Yes| H
    H --> I
    I --> J
```
