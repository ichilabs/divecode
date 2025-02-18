---
title: "Advanced Data Modeling: Database Modeling"
date: "2025-02-11"
authors:
  - "jathurchan"
projects:
  - "55"
---

- Data modeling: developing visual representation of data elements and their relationships.
  - Conceptual data model

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/DF59FA73-9B1B-48DD-9F09-1C78C6229A8B_2/qijMhxfvIQKxvjjg6cgcbhKSXidUDWUO6tbAxdEouysz/Image.png)

- Logical data model

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/884956A5-297C-4D96-BB7A-CCABEF1D7D0C_2/oUv4dSDcDpyATVPAmJLZpO5VqBFLkp9AvuEuw4XGQ4oz/Image.png)

- physical data model (data types, constraints, attributes)

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/EB98874B-BE5D-44A2-A8EA-98DF777E417F_2/cJZbEysU46po8yuS2nMPtJqxe59gdHoVuZk2oLCFa4cz/Image.png)

- Types of data models
  - Relational data model

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/DA1A919F-0745-43F5-8E91-0A8C4CC9A9EB_2/XvC8DCvTLxGwUHy6h2fe29odLf2yoLiWh2pRBPk79MIz/Image.png)

- Entity relationship model (ER diagram)

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/BFD06311-7CD3-4FDB-BE85-8F4B221F68E2_2/jNa5gMUNHjyJxSOhNHhx5oWvLUMpKcIMR9v3tcTnCjkz/Image.png)

- Hierarchical data model (tree-like / parent-child structure, only permits one-to-many relationships between nodes but navigating through the database quickly and efficiently)

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/EF698151-810E-460F-A04F-B472EF9C59E5_2/RHfrcTCo9LqIMdjk2p3aCkBqGy2e8zz4bmykZ3VgAUAz/Image.png)

- Object-oriented data model (different types of associations like aggregations, compositions, and inheritance)

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/A706CBF3-94B7-4E74-B1C8-5F67ECD67A10_2/Uu7ugmG4ZAKr1Ao2x8SAckNfBWB9YzMoqV1xg30ab4kz/Image.png)

- Dimensional data model

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/6525026D-31AF-4E69-8E3D-DFC4704C27F5_2/TVxYAaCQpgzdyMm6x0fiWqfbnDHiyH0cPVAs3uA7KhYz/Image.png)

- Normalization
  - enables
    - reduce duplication
    - avoid data modification implications
    - simplify queries
  - Avoids
    - Insertion anomaly: new data requires the insertion of additional data.
    - Update anomaly: an update of a record results in further updates.
    - Deletion anomaly: a deletion of a record deletes more than one data set.
  - how
    - 1st normal form (enforces data atomicity and eliminates unnecessary repeating data groups)

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/1FD594FB-545C-4C4F-A2DA-56D7AA414E6D_2/pcicrCSLYU5fCwBj8t06XMMv47mi2HRlP7hXTAeROwoz/Image.png)

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/09DEBB01-6981-4DF8-B921-A4E96EEA106E_2/qJrspxKgxwFSxJfdtxNw09lFwBkhMBraGeRV4ZbZ7Qkz/Image.png)

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/8DBB66FB-D0C1-4CF9-BCB1-E50D102CA9DC_2/a9K4R2i5LkOwPsexyeoGqYYJ3a1Lx1XBiC4ZfkpiVgAz/Image.png)

      - 2nd normal form (a table cannot contain any relationships built on functional or partial dependency)

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/5E42CCE0-8709-4A25-AAF0-15722F1187E4_2/ODZT1ckqyDsF1qLO09Pzp6dkiKy6yLyQLSvl0ZfCLbkz/Image.png)

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/5DA92366-3393-4196-BA00-6BD2C655014C_2/xIAJi9873fCATgHF4vP93RLj13gjI773yp2eTtxHjysz/Image.png)

      - 3rd normal form (resolve issues of transitive dependency, when non-key attributes depend on one another)

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/A213BCC8-3B6B-4ED2-A405-3DF79E96AF16_2/jXBXUm4ssmsp2CauGkRG6nomuYpmzdyPuXgjscBjXmwz/Image.png)

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/54418EF7-0A33-433A-AF80-5E6DE488944D_2/xONTc29y5IJwzrOM6xWFc1Wuw4Ox5AnjaBJz632AkRUz/Image.png)

- Design a database model for:

| **Order ID** | **Client name** | **Client address** | **Order Date** | **Delivery Status** | **Delivery Date** | **Contact Number** | **Email** | **Item name** | **Item price** | **Total cost** |
| ------------ | --------------- | ------------------ | -------------- | ------------------- | ----------------- | ------------------ | --------- | ------------- | -------------- | -------------- |
| Data         | Data            | Data               | Data           | Data                | Data              | Data               | Data      | Data          | Data           | Data           |
| Data         | Data            | Data               | Data           | Data                | Data              | Data               | Data      | Data          | Data           | Data           |
| Data         | Data            | Data               | Data           | Data                | Data              | Data               | Data      | Data          | Data           | Data           |
| Data         | Data            | Data               | Data           | Data                | Data              | Data               | Data      | Data          | Data           | Data           |

![Image.jpeg](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/05282AD4-99CA-4892-B8A5-516AA4EEA5D5_2/kn0k9OpP3SN70Svx8XYkQ0zcJHOGO4MVXle32uKPs5Ez/Image.jpeg)

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/17FD7F83-D4CA-4C18-8EC6-33A6F5491D4E_2/FLP7n3kwzuFRSyp3RZdyEaMZy2JZq6hfmz6RqwnByVAz/Image.png)

- Some clients could have multiple delivery addresses:

![Image.png](https://res.craft.do/user/full/220382df-dd92-deed-f543-c34c29908bbc/doc/B03E5A24-6A72-4300-ABF6-F1F68CE1DB1B/A1864854-EF43-4D2B-865B-AAFB2E0CAE69_2/S5xcMTgPRMOk41TgYdlxT2Rf9baBEcZLlYU8TVqvoYEz/Image.png)
