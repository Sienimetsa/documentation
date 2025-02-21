```mermaid
erDiagram
    Mushroom {
        int m_id PK
        string m_name
        string toxicity_level
        string color
        string gills
        string cap
        string taste
    }
    
    User {
        int user_id PK
        string username
        string password
        string phone
        string mail
        string country
    }
    
    Finding {
        int finding_id PK
        int user_id FK
        int m_id FK
        string time
        string city
        string notes
    }
    
    Mushroom ||--o{ Finding : "1..*"
    User ||--|| Finding : "1"
