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

UPDATE postac
SET wiek = 88
WHERE nazwa = 'Tesciowa';

```
# zad 2
```sql
CREATE TABLE walizka (
    id_walizki INT AUTO_INCREMENT PRIMARY KEY,
    pojemnosc INT UNSIGNED,
    kolor ENUM('różowy', 'czerwony', 'tęczowy', 'żółty'),
    id_wlasciciela INT,
    FOREIGN KEY (id_wlasciciela) REFERENCES postac(id_postaci) ON DELETE CASCADE
);

ALTER TABLE walizka
MODIFY kolor ENUM('różowy', 'czerwony', 'tęczowy', 'żółty') DEFAULT 'różowy';

```
# zad 3
```sql
CREATE TABLE izba (
    adres_budynku VARCHAR(100),
    nazwa_izby VARCHAR(50),
    metraz INT UNSIGNED,
    wlasciciel INT,
    PRIMARY KEY (adres_budynku, nazwa_izby),
    FOREIGN KEY (wlasciciel) REFERENCES postac(id_postaci) ON DELETE SET NULL
);

ALTER TABLE izba
ADD COLUMN kolor_izby VARCHAR(20) DEFAULT 'czarny' AFTER metraz;

INSERT INTO izba (adres_budynku, nazwa_izby, metraz, wlasciciel)
VALUES ('ul. Bohatera', 'spiżarnia', 10, NULL);

```

# zad 4
```sql

CREATE TABLE przetwory (
    id_przetworu INT AUTO_INCREMENT PRIMARY KEY,
    rok_produkcji YEAR DEFAULT 1654,
    id_wykonawcy INT,
    zawartosc VARCHAR(255),
    dodatek VARCHAR(50) DEFAULT 'papryczka chilli',
    id_konsumenta INT,
    FOREIGN KEY (id_wykonawcy) REFERENCES postac(id_postaci),
    FOREIGN KEY (id_konsumenta) REFERENCES postac(id_postaci)

INSERT INTO przetwory (rok_produkcji, id_wykonawcy, zawartosc, id_konsumenta)
VALUES (1654, NULL, 'bigos', NULL);

```
