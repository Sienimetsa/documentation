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
        string description
    }
    
    User {
        int user_id PK
        string username FK
        string password
        string phone
        string mail
        string country
        string profilepicture
        string chatcolor
        int level
        decimal progress
    }

    User_Unique_Mushrooms {
        int u_id PK
        int m_id PK
    }

    Message {
        int id PK
        string text
        timestamp timestamp
    }
    
    Finding {
        int finding_id PK
        int user_id FK
        int m_id FK
        string time
        string city
        string notes
    }

User ||--o{ User_Unique_Mushrooms : "1..*"
Mushroom ||--o{ User_Unique_Mushrooms : "1..*"
User ||--o{ Message : "1..*"
User ||--|| Finding : "1..*"
Mushroom ||--o{ Finding : "1..*"
