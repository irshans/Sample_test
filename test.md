```mermaid
flowchart TD
    A[Start: Input Parameters] --> B[Build JSON Request]
    B --> C[Set API URL]
    C --> D[Try HTTP POST to Google API]
    D -->|Success| E[Get Response JSON]
    D -->|Failure| F[Handle Error & Exit]
    E --> G[Parse Validation Granularity & Address Complete]
    G -->|Valid & Complete| H[Set Output Parameters]
    G -->|Invalid| I[Set APIStatus as Invalid]
    H --> J[Extract Address Components]
    J --> K[Set Output: City, State, PostalCode, County, DPVConfirmation]
    K --> L[Set MapURL]
    L --> M[Return Results]
    I --> M
    F --> M
