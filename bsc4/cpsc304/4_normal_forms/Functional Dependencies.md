# Functional Dependency
- In a functional dependency, a set of attributes determines other attributes, e.g., $(A, B) \Rightarrow C$, means A and B together determine C  
- A trivial FD determines what you already have, eg., $(A, B) \Rightarrow B$
- A key is a minimal set of attributes determining the rest of the attributes of a relation  
- For example, R(House #, Street, City, Province, Postal Code)  
- A superkey is a set of attributes determining the rest of the attributes in the relation, but does NOT have to be minimal (e.g., the key above, or adding in either of City and Province)  
- Given a set of (explicit) functional dependencies, we can determine   others...