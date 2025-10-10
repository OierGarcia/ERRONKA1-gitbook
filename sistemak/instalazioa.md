# ⚙️ Instalazioa – Sistema nagusien konfigurazioa

**Helburua:**\
Windows eta Linux zerbitzu-sistemak instalatu eta konfiguratu, enpresako sareko egitura eta zerbitzuak oinarritik ezartzeko.

**🪟 Windows Server – Active Directory eta taldeak**

* Domeinua: `puneta.eus`
* Zerbitzaria: `puñetaserver.puneta.eus`
* Rolak:
  * **Active Directory Domain Services (AD DS)**
  * **DNS eta DHCP zerbitzuak**
  * **Inprimaketa zerbitzua (Print Services)**

**Erabiltzaileen eta taldeen egitura:**

* **Organizational Units (OU):**
  * `puneteros/langileak`
  * `puneteros/ikasleak`

**Talde nagusiak eta erabilerak:**

* `PrintAdmins` → Inprimagailuak administratzeko baimen osoak
* `PrintUsers` → Dokumentuak inprimatzeko baimena
* `VPN_Users` → VPN bidez konektatzeko erabiltzaileak
* `Teachers`, `IT_Admins`, `HR`, `Finance`, `DockerUsers`, `GitUsers` → sail edo funtzio bakoitzerako talde bereiziak

**Adibidea:**

* _student_ taldean sartuta dauden erabiltzaileak: Ane, Gorka, Naia eta Xabier.
* Talde bakoitzak bere karpetak eta baliabideak ditu domeinu barruan esleituta.
