# ⚙️ Datu Base

####

**Helburua:** Sortutako datu-basearen ustiapena eta erabiltzaileen baimenak konfiguratzea.

**Egindako lana:**\
MySQL-en erabiltzaile desberdinak sortu dira, bakoitzari bere **rol eta baimen egokiak** esleituta:

* `usuario_clientes`: bezeroei buruzko datuak kudeatzeko.
* `usuario_productos`: produktuen kudeaketa.
* `usuario_ventas`: salmentak eta salmenta xehetasunak.
* `usuario_compras`: erosketak eta xehetasunak.
* `usuario_contabilidad`: datu guztiak ikusteko baina ez aldatzeko.
* `usuario_admin`: EMPRESA datu-base osoaren kudeatzaile osoa.

```
CREATE USER 'usuario_clientes'@'localhost' IDENTIFIED BY 'Admin123';
GRANT SELECT, INSERT, UPDATE, DELETE ON EMPRESA.clientes TO 'usuario_clientes'@'localhost';
```

**Gainera**, GLPI eta WordPress sistemetarako datu-baseak ere sortu dira, bakoitzak bere erabiltzailearekin:

* **GLPI:** `CREATE DATABASE glpi; GRANT ALL PRIVILEGES ON glpi.* TO 'administrador'@'localhost';`
* **WordPress:** `CREATE DATABASE WORDPRESS; GRANT ALL PRIVILEGES ON WORDPRESS.* TO 'administrador'@'localhost';`

**Azalpena:**\
Eragiketa guztiak MySQL terminalean egin dira Ubuntu zerbitzarian, eta emaitza dokumentatu da. Egindako konfigurazioarekin sistemek (GLPI eta WordPress) behar bezala funtzionatu dute.
