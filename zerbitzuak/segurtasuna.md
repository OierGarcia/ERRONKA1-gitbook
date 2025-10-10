# 🔒 Segurtasuna – Babesa eta Berreskurapena



**🔹 1. Firewall eta Portuak**

**Ubuntu zerbitzarian (UFW):**

```bash
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw allow 3478/udp
sudo ufw allow 5349/tcp
sudo ufw allow 10000/udp
sudo ufw --force enable
sudo ufw status
```

**Windows zerbitzarian:**

* Firewall aktibo dago barne eta kanpo trafikoa kontrolatzeko.
* Portu baimenduak:
  * **53 (DNS)**
  * **67/68 (DHCP)**
  * **80/443 (HTTP/HTTPS)**
  * **3389 (RDP, soilik administrazio sarbidea)**

**🔹 2. Ziurtagiriak**

* Jitsi zerbitzuan **Let’s Encrypt** HTTPS ziurtagiria instalatu da:\
  `/usr/share/jitsi-meet/scripts/install-letsencrypt-cert.sh`
* Windows domeinuaren barruan **Active Directory Certificate Services** moduluaren bidez kudeatzen dira ziurtagiri lokalak.

**🔹 3. Egoeraren egiaztapenak**

Zerbitzuen egoera egiaztatzeko komando nagusiak:

```bash
sudo systemctl status prosody
sudo systemctl status jicofo
sudo systemctl status jitsi-videobridge2
sudo ss -tulpen | egrep '(:80|:443|:10000|:3478|:5349)'
```

Eta logak ikusteko:

```bash
sudo journalctl -u prosody -f
sudo journalctl -u jicofo -f
sudo journalctl -u jitsi-videobridge2 -f
```

Windowsen, “Event Viewer” eta “Server Manager” erabilita egiaztatzen dira zerbitzuak eta sarea.

***

**🔹 4. Pasahitzen Politika**

**Arau orokorrak:**

* Gutxienez 10–12 karaktere (maiuskula, minuskula, zenbaki eta sinboloa).
* Ez da onartzen datu pertsonalak edo aurreko pasahitzak berrerabiltzea.
* Pasahitzaren balio-epea: **90 egun**.
* 5 saiakera okerren ondoren kontua blokeatzen da.
* Lehenengo saioan pasahitza aldatu behar da.
* Ez dira errepikatzen azken 5 pasahitzak.

**Kontu bereziak:**

* Zerbitzu-kontuak dokumentatu behar dira (“Password never expires”).
* Administratzaileek **bi faktoreko autentifikazioa** eta **hileko aldaketa** dute.

**Adibide egokiak:**

```
Admin123!AG21
Tienda#2024%Segura
PñtR0s!Tech@45
```

**Gehigarriak:**

* Gomendatutako pasahitz kudeatzaileak: _KeePassXC_ edo _Bitwarden_.
* Langileei phishing eta kredentzialen lapurreten aurkako prestakuntza ematen zaie.
* Politika hau urtean behin berrikusten da eta Active Directory-n aplikatzen du sistemaren administratzaileak.

***

**🔹 5. Kontingentzia Plana**

**Helburua:**\
Puñeteros S.L.-ren sistema kritikoak berriz martxan jartzea gorabehera larrien kasuan.

**Aktibo kritikoak:**

* Windows Server (AD, DNS, DHCP, inprimaketa)
* Linux zerbitzaria (WordPress eta Jitsi)
* Datu-base zerbitzaria (MySQL / MariaDB)
* Sare azpiegitura (switch, router, firewall, VPN)
* Datu sentikorrak: bezeroak, fakturazioa, inbentarioa

**Arriskuak:**

* Zibererasoak (phishing, ransomware, baimenik gabeko sarbidea)
* Giza akatsak eta konfigurazio okerrak
* Hardware matxurak edo hornidura elektrikoaren etenak
* Hondamendi fisikoak (sutea, uholdeak, lapurreta)

**Neurri prebentiboak:**

* Eguneroko **babeskopiak**
* **UPS** (alimentazio etenik gabea)
* **Firewall, IDS eta VPN**
* **Antibirus eguneratua**
* **Pasahitz politika zorrotzak**
* **Sarbide fisikoaren kontrola** (kamerak, giltzak)

**Berreskuratze plana:**

* **RTO:** zerbitzari kritikoak ≤ 4 ordu, PCak ≤ 24 ordu
* **RPO:** datu sentikorrak ≤ 1 egun
* **Prozesua:**
  1. Intzidentzia identifikatu
  2. Babeskopiak aktibatu
  3. Sare → BD → AD → Web ordenean leheneratu
  4. Bezeroei jakinarazi

**Arduradunak:**\
Sistemaren administratzailea, dendako arduraduna eta zuzendaritza.
