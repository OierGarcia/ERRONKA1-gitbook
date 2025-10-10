# 🔧 Mantenua – Sistema eta inprimagailuen kudeaketa

* .

***

**Helburua:**\
Sistemak eta zerbitzuak eguneratuta eta erabilgarri mantentzea, bai Windows bai Linux inguruetan.

**🧾 CUPS inprimaketa-sistema (Linux zerbitzaria)**

Linux sistemetan inprimagailuen kudeaketa **CUPS** (_Common Unix Printing System_) bidez egiten da.\
Zerbitzu honek inprimagailu lokalak eta sarekoak administratzeko aukera ematen du, baita urruneko kontrola ere.

**Instalazioa:**

```bash
sudo apt update
sudo apt install cups -y
```

**Konfigurazioa:**

* Fitxategiak `/etc/cups/` direktorioan daude.
*   Urruneko sarbidea gaitzeko, editatu `/etc/cups/cupsd.conf` eta gehitu:

    ```
    Listen 0.0.0.0:631
    <Location />
        Allow All
    </Location>
    ```

    Ondoren, berrabiarazi:

    ```bash
    sudo systemctl restart cups
    ```

**CUPS interfazea:**

* Nabigatzailetik sartzeko:\
  `http://zerbitzariaren_IPa:631`\
  edo\
  `http://zerbitzariaren_izena:631`

**Zerbitzuaren egoera egiaztatzeko:**

```bash
sudo systemctl status cups
```

**Erabiltzaileen kudeaketa:**\
Inprimagailuak instalatzeko erabiltzaileak `lpadmin` taldean egon behar dira:

```bash
sudo usermod -aG lpadmin erabiltzailea
```

