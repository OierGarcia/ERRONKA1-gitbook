# 🖨️ Monitorizazioa  Inprimagailuak Windows eta Ubuntu artean

**🖨️ Inprimagailuak Windows eta Ubuntu artean**

* Zerbitzaria: `WSERVER-NEREA`
* Inprimagailuak: _Inprimagailua\_1_ eta _Inprimagailua\_2_
* Taldeak eta baimenak:
  * **PrintUsers** → Inprimatzeko baimena soilik.
  * **PrintAdmins** → Inprimagailuak eta dokumentuak kudeatzeko baimen osoak.
  * Gainerako erabiltzaileei baimenak kenduta.

**Baimenen adibidea:**

* _PrintUsers_: “Inprimatu” baimena.
* _PrintAdmins_: “Inprimatu”, “Dokumentuak administratu” eta “Inprimagailua kudeatu”.

**Ubuntu-tik inprimaketa probak:**

* CUPS web interfazetik gehitu inprimagailua.
* Proba inprimaketa: “Inprimagailua\_1\_servidor” bidez.
* Egoera: _Prepared / Ready_.

***

#### 📊 **Monitorizazioa – Sistema eta zerbitzuen egoera**

**Helburua:**\
Sareko eta zerbitzuen egoera kontrolatzea eta log-ak aztertzea, ustekabeko akatsak prebenitzeko.

**🧠 Linux zerbitzariaren monitorizazioa**

**Komando erabilienak:**

```bash
sudo systemctl status prosody
sudo systemctl status jicofo
sudo systemctl status jitsi-videobridge2
sudo systemctl status cups
sudo ss -tulpen | egrep '(:80|:443|:631|:10000)'
```

**Logen jarraipena zuzenean:**

```bash
sudo journalctl -u cups -f
sudo journalctl -u apache2 -f
sudo journalctl -u mysql -f
```

**🪟 Windows zerbitzariko monitorizazioa**

* **Server Manager** → zerbitzu aktiboen egoera
* **Event Viewer** → akatsen, sarbideen eta hardwarearen logak
* **Task Manager** eta **Performance Monitor** → baliabideen erabilera (% CPU, RAM, diskoa)

**🧩 Mantentze-prebentzioa**

* Sistema eguneratze automatikoak konfiguratuta (Windows Update eta `apt upgrade`).
* CUPS, Apache eta Jitsi zerbitzuak automatikoki abiarazten dira sistemaren hasieran.
* Babeskopiak eta erregistroak astean behin aztertzen dira.

**Ondorioa:**\
Sistemaren funtzionamendu egonkorra eta sareko zerbitzu guztien jarraipen aktiboa bermatzen dira, bai Windows ingurunean bai Ubuntu zerbitzarian.
