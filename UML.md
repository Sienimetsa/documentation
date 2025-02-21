erDiagram

    Mushroom {
        string m_id PK
        string m_name
        string toxicity_level
        string color
        string gills
        string cap
        string taste
    }
    
    User {
        string user_id PK
        string username
        string password
        string phone
        string mail
        string country
    }
    
    Finding {
        string user_id PK, FK
        string m_id PK, FK
        string time
        string city
        string notes
    }
    
    Mushroom ||--o{ Finding : has
    User ||--o{ Finding : records
    Mushroom |o--o{ Finding : "1..*"
