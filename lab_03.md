## Lab 4

# zad 1 
```sql
create table postac(
	id_postaci int primary key,
    nazwa varchar(40),
    rodzaj enum('wiking','ptak','kobieta'),
    date_ur date,
    wiek int unsigned);
    
INSERT INTO postac (nazwa)
VALUES (Bjorn, Drozd, Tesciowa)
```
