![[Pasted image 20220927155657.png]]

```sql
CREATE TABLE WorkOn(  
    MPID CHAR(11),  
    MID INTEGER,  
    Role CHAR(20),  
    PRIMARY KEY (MPID, MID),  
    FOREIGN KEY (MPID)  
        REFERENCES MoviePeople,  
    FOREIGN KEY (MID)  
        REFERENCES Movies)
```