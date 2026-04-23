[Powrót](README.md)

-----

# Konfiguracja VPN (Instytut Informatyki)

Szybka instrukcja konfiguracji połączenia VPN do sieci studenckiej II.

### 1\. Zgłoszenie dostępu

Wyślij e-mail z prośbą o aktywację usługi VPN **(koniecznie z adresu `@uni.wroc.pl`)**

  * **Do:** `admin@ii.uni.wroc.pl`
  * **Temat:** `VPN`

**Treść:**

```text
Dzień dobry,
proszę o aktywowanie dostępu do VPN sieci studenckiej.

Pozdrawiam, 😊
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
| **Serwer / Brama** | `156.17.4.253` |
| **Login** | Ten sam co w pracowniach (np. `i123456`) |
| **Hasło** | To samo co w pracowniach |

-----
