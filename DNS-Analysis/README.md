# DNS-Auflösung mit Wireshark – Beispiel www.heise.de

Dieses Projekt zeigt anhand eines Wireshark-Mitschnitts, wie die DNS-Auflösung einer Domain (hier: **www.heise.de**) funktioniert.  
Es wird demonstriert, welche Anfragen ein Client an den DNS-Server stellt und welche Antworten zurückgegeben werden.

<img width="1167" height="254" alt="{46131E25-A153-4DE5-A2CC-E2196A0B3F15}" src="https://github.com/user-attachments/assets/65c6c215-84a8-4055-95f4-420da3d15a41" />


## Ablauf der DNS-Auflösung
1. **Client** (192.168.2.34) sendet DNS-Query an **DNS-Server** (192.168.2.1):
   - `AAAA www.heise.de` → Anfrage nach IPv6-Adresse  
   - `A www.heise.de` → Anfrage nach IPv4-Adresse  
   - `HTTPS www.heise.de` → Anfrage nach HTTPS-Service-Informationen  

2. **DNS-Server** antwortet mit:
   - IPv4: `193.99.144.85`  
   - IPv6: `2a02:2e0:3fe:1001:7777:772e:2:85`  
   - SOA-Record: `ns.heise.de` (Start of Authority)

3. Der Client kann nun mit den erhaltenen IP-Adressen eine Verbindung zu **www.heise.de** herstellen.

