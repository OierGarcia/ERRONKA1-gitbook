# 🧱 Konfigurazioa – Windows Server Zerbitzuak

**Helburua:**\
Puñeteros S.L.-ren sare eta domeinu zerbitzuak Windows Server-en bidez zentralizatzea: DHCP, DNS eta Active Directory.

**1️⃣ Active Directory eta Domeinua**

* Domeinua: `puneta.eus`
* Zerbitzaria: `puñetaserver.puneta.eus`
* Kontrolatzailea: `WSERVER-NEREA`
* Rola: **Active Directory Domain Services (AD DS)**

Instalazioan domeinu berria sortu da eta erabiltzaileak, taldeak eta politika orokorrak (GPO) konfiguratu dira.

**2️⃣ DNS konfigurazioa**

DNS zerbitzarian sortu diren erregistroak:

* **Host (A):** `www` → 192.168.10.1
* **Alias (CNAME):** `ftp` → [www.puneta.eus](http://www.puneta.eus)
* **Host gehigarriak:**
  * `jitsi` → 192.168.10.3
  * `wserver-nerea` → 192.168.10.1

DNS honek domeinu barneko zerbitzu guztiak izen bidez ebaztea ahalbidetzen du.

**3️⃣ DHCP konfigurazioa**

IP helbide dinamikoak automatikoki banatzeko konfigurazioa:

```
Hasierako IP: 192.168.10.50
Amaierako IP: 192.168.10.70
Maskara: 255.255.255.0
```

Horrela, sareko bezeroek IP helbide egokiak jasotzen dituzte automatikoki.

**4️⃣ Beste zerbitzuak**

* **Inprimaketa zerbitzua** eta **IIS (Web Zerbitzaria)**\
  Barne-aplikazioetarako eta fitxategien partekatzera bideratuta.
