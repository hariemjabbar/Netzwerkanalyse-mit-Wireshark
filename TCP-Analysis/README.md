# TCP-Handshake mit Wireshark am Beispiel www.heise.de

Dieses Projekt zeigt mit Hilfe von **Wireshark**, wie die Auflösung einer Domain in eine IP-Adresse per DNS erfolgt und wie anschließend der **TCP-Handshake** zum Aufbau der Verbindung durchgeführt wird.  
Als Beispiel dient die Webseite **www.heise.de**.

<img width="1232" height="112" alt="{AD26CCE7-5AF6-4FCC-BFFC-D8BF269D1822}" src="https://github.com/user-attachments/assets/591bcae6-3c44-4b2f-943c-a338edf2ac2a" />


## 🔎 TCP-Handshake (3-Way Handshake)
Nach der DNS-Auflösung baut der Client eine TCP-Verbindung zum Heise-Server auf.  

### Ablauf im Wireshark-Mitschnitt:
1. **SYN** – Client → Server  
   *Frame 623*: `2003:e0:3fe1:... → 2a02:2e0:3fe:... [SYN]`  
   → Der Client möchte eine Verbindung aufbauen.
2. **SYN, ACK** – Server → Client  
   *Frame 642*: `2a02:2e0:3fe:... → 2003:e0:3fe1:... [SYN, ACK]`  
   → Der Server akzeptiert und bestätigt.

3. **ACK** – Client → Server  
   *Frame 644*: `2003:e0:3fe1:... → 2a02:2e0:3fe:... [ACK]`  
   → Der Client bestätigt die Verbindung.

Damit ist die TCP-Verbindung erfolgreich aufgebaut.
