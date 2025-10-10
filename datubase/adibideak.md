# 🧩 Datu Base

**Adibidea 1 – Bezero berria sartzea:**

```
INSERT INTO bezeroak (izena, telefonoa, emaila, helbidea)
VALUES ('Jon Ander', '600123123', 'jon@empresa.com', 'Bilbo, Euskadi');
```

**Adibidea 2 – Produktu baten stocka eguneratzea:**

```
UPDATE produktuak SET stock = stock - 2 WHERE id = 5;
```

**Adibidea 3 – Salmenta bat egitea:**

```
INSERT INTO salmentak (data, bezero_id, langile_id, guztira)
VALUES (CURDATE(), 1, 2, 159.90);
```

**Adibidea 4 – Baimenak egiaztatzea:**

```
SHOW GRANTS FOR 'usuario_ventas'@'localhost';
```
