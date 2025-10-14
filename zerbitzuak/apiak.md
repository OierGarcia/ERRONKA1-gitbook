# 🧩 APlak – Jitsi Zerbitzua Ubuntu

**Helburua:**\
Bideo-konferentzia plataforma propioa instalatu eta konfiguratu, **jitsi.puneta.eus** domeinuaren bidez erabilgarri egon dadin.

**Instalazio prozesua:**\
Ubuntu 24.04 zerbitzarian **Jitsi Meet** instalatu da urrats hauen bidez:

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y ufw
sudo ufw allow OpenSSH
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw allow 5349/tcp
sudo ufw allow 3478/udp
sudo ufw allow 10000/udp
sudo ufw --force enable
```

**Errepositorioa gehitzea:**

```bash
curl -fsSL https://download.jitsi.org/jitsi-key.gpg.key -o jitsi-key.gpg.key
sudo gpg --yes --output /usr/share/keyrings/jitsi-key.gpg --dearmor jitsi-key.gpg.key
echo "deb [signed-by=/usr/share/keyrings/jitsi-key.gpg] https://download.jitsi.org stable/" | sudo tee /etc/apt/sources.list.d/jitsi-stable.list
sudo apt update
```

**Instalazioa eta konfigurazioa:**

```bash
sudo apt install -y jitsi-meet
```

Instalatzaileak galdetutakoan, domeinua ezarri da:\
`jitsi.puneta.eus`\
eta hasieran **self-signed certificate** bat erabili da.

Ondoren, zerbitzuen egoera egiaztatu da:

```bash
sudo systemctl status prosody
sudo systemctl status jicofo
sudo systemctl status jitsi-videobridge2
```

**HTTPS ziurtagiria (Let’s Encrypt):**

```bash
sudo /usr/share/jitsi-meet/scripts/install-letsencrypt-cert.sh
```

**DNS konfigurazioa (Windows Server):**\
Windows Server zerbitzarian, **DNS** konfiguratu da, **192.168.71.2** IP helbidea zuzenean bilatu beharrean, **jitsi.puneta.eus** domeinua erabil dadin.

**Emaitza:**\
Zerbitzua behar bezala dabil eta [**https://jitsi.puneta.eus**](https://jitsi.puneta.eus) helbidean erabil daiteke, barruko eta kanpoko sarerako (VPN bidez).
