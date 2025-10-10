# ⚙️ Datu Base → Eragiketak

**Helburua:**\
Sortutako datu-basearen ustiapena eta erabiltzaileen baimenak konfiguratu, bai **Ubuntu zerbitzari batean** bai **ordenagailu lokalean**, WordPress eta GLPI aplikazioetarako.

**Egindako lana:**\
MySQL edo MariaDB erabiltzen duen ingurunearen arabera (Ubuntu server edo lokala), datu-baseak eta erabiltzaileak sortu dira, segurtasuna eta baimen egokiak bermatuz.

Erabiltzaile bakoitzari bere **rol funtzionala** esleitu zaio:

* `usuario_clientes`: bezeroak kudeatzeko.
* `usuario_productos`: produktuen eta stockaren kudeaketa.
* `usuario_ventas`: salmenten eta xehetasunen kudeaketa.
* `usuario_compras`: erosketen eta xehetasunen kudeaketa.
* `usuario_contabilidad`: datuak kontsultatzeko baina ez aldatzeko.
* `usuario_admin`: EMPRESA datu-base osoaren administratzaile osoa.

**Adibide praktikoak:**

```
CREATE USER 'usuario_clientes'@'localhost' IDENTIFIED BY 'Admin123';
GRANT SELECT, INSERT, UPDATE, DELETE ON EMPRESA.clientes TO 'usuario_clientes'@'localhost';
```

**WordPress eta GLPI aplikazioetarako:**\
Bi sistemek beren datu-base propioa dute, bai **Ubuntu zerbitzarian** instalatuta badago, bai **localhost** bidez XAMPP, LAMP edo Laragon erabiliz:

*   **WordPress:**

    ```
    CREATE DATABASE WORDPRESS;
    CREATE USER 'administrador'@'localhost' IDENTIFIED BY 'Admin123';
    GRANT ALL PRIVILEGES ON WORDPRESS.* TO 'administrador'@'localhost';
    FLUSH PRIVILEGES;
    ```
*   **GLPI:**

    ```
    CREATE DATABASE glpi CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
    CREATE USER 'administrador'@'localhost' IDENTIFIED BY 'Admin123';
    GRANT ALL PRIVILEGES ON glpi.* TO 'administrador'@'localhost';
    FLUSH PRIVILEGES;
    ```

**Azalpena:**\
Eragiketa guztiak MySQL terminalean edo phpMyAdmin bidez egin dira.\
Instalazioa **Ubuntu Server**-en edo **lokalean** egin izanak ez du funtzionaltasunean eraginik: bi kasuetan datu-baseak behar bezala konektatu dira eta erabiltzaile bakoitzak bere baimen-maila du.

**Ondorioa:**\
Erabiltzaile eta baimen guztiak behar bezala dokumentatu dira, eta WordPress zein GLPI sistemek datu-basearekin konexio egonkorra eta segurua dute.
