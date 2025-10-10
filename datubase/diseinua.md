# 🧱 Datu Base

**Helburua:** Enpresa baten datu-basearen diseinua egitea, bezeroak, produktuak, salmentak eta erosketak kudeatzeko.

**Egindako lana:**\
Lehenik, **EMPRESA** izeneko datu-basea sortu dut MySQL-en. Datu-basearen diseinuan, entitate eta erlazio nagusiak identifikatu dira:

* **Bezeroak**, **Langileak**, **Hornitzaileak**, **Produktuak**, **Salmentak** eta **Erosketak**.\
  Horietako bakoitzak bere **atributuak** eta **gako nagusiak** ditu, eta taulen arteko erlazioak **kanpo-gakoekin (FOREIGN KEY)** ezarri dira.\
  Diseinua **normalizatu** egin da datuen errepikapena saihesteko eta osotasuna bermatzeko.

**Laburpena:**

```
CREATE DATABASE EMPRESA;
USE EMPRESA;

CREATE TABLE bezeroak (...);
CREATE TABLE langileak (...);
CREATE TABLE produktuak (...);
CREATE TABLE salmentak (...);
CREATE TABLE salmenta_xehetasunak (...);
```

**Justifikazioa:**\
Egitura hau hautatu da kudeaketa erraza, datuen koherentzia eta eskalagarritasuna bermatzeko. Gainera, DBaren erabiltzaile bakoitzak behar duen **baimen maila** ere zehaztu da (ikus “Eragiketak” atala).
