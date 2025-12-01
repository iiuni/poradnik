[Powrót](README.md)

-----

# Konfiguracja VPN (Instytut Informatyki)

Szybka instrukcja konfiguracji połączenia VPN do sieci wydziałowej.

### 1\. Zgłoszenie dostępu

Wyślij wiadomość z prośbą o aktywację usługi VPN.

  * **Do:** `admin@ii.uni.wroc.pl`
  * **Temat:** `VPN`

**Treść:**

```text
Dzień dobry,
Chciałbym prosić o umożliwienie mi połączenia do VPN.
Pozdrawiam,😊
```

### 2\. Konfiguracja Firewalla

Aby połączenie działało poprawnie, wykonaj jedną z poniższych czynności:

  * Dodaj reguły przepuszczające ruch VPN (protokół GRE / port 1723).
  ```bash
  sudo firewall-cmd --permanent --add-port=1723/tcp
  sudo firewall-cmd --permanent --add-protocol=gre
  ```
  * Lub (tymczasowo) wyłącz zaporę ogniową.

### 3\. Ustawienia klienta

Skonfiguruj nowe połączenie VPN w systemie, używając poniższych parametrów:

| Ustawienie | Wartość |
| :--- | :--- |
| **Typ/Protokół** | PPTP (Point-to-Point Tunneling Protocol) |
| **Serwer / Brama** | `156.17.4.252` |
| **Login** | Twój login wydziałowy |
| **Hasło** | Twoje hasło wydziałowe |

-----
