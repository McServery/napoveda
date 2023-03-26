---
description: >-
  Přidal server, který vlastníte jiný uživatel? Pomocí tohoto nástroje je možné
  nárokovat vlastnictví serveru. K převodu je nutné abyste měli přístup ke
  konfiguračnímu souboru serveru.
---

# Převod vlastnictví serveru

Před převodem serveru je důležité vědět, že **bude smazán popis serveru, api key a také bude server skryt.** Po převodu je tedy nutné server editovat a vložit popis serveru.

Popis serveru, je nutné znovu vložit z důvodu, aby byl aktuální. Rovněž je z bezpečnostních důvodů smazán api key serveru, pokud byl v minulosti vygenerován.

### Kdy použít převod vlastnictví serveru?

Převod vlastnictví serveru se zejména hodí, pokud Váš server přidal jiný uživatel a Vy chcete získat kontrolu nad tím, jak je na server listu prezentován nebo odměnit hráče za hlasování prostřednictvím Votifieru.

Rovněž je možné použít převod serveru, pokud například změnil majitele nebo ho na server list přidal administrátor serveru který již na projektu nespolupracuje.

### Co potřebuji k převodu?

K převodu serveru není nutná spolupráce uživatele, který server na server list přidal. Je však nutné mít přístup na FTP nebo mít jinou možnost, jak v administraci Vašeho hostingu změnit konfigurační soubor serveru.

1. Přihlaste se ke svému účtu na mcservery.eu a přejděte na detail serveru kde chcete nárokovat vlastnictví
2. V panelu na pravé straně se nachází informace o serveru (verze, počet hlasů a pod..) klikněte na vlaječku.  <img src="../.gitbook/assets/image.png" alt="" data-size="line">
3. Otevřete soubor <mark style="color:red;">`server.properties`</mark>
4. Smažte popis serveru a vložte kód na řádek 33 kde by měla být vlastnost <mark style="color:red;">`motd=`</mark>&#x20;
5. Uložte změnu a restartujte server nebo znovu konfigurační soubor načtěte pomocí příkazu <mark style="color:red;">`/reload`</mark>
6.  Postupujte dále v nastavení uživatelského účtu na mcservery.eu&#x20;

    <figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

### FAQs

<details>

<summary>Po převodu server zmizel, čím to je?</summary>

Převod musí potvrdit administrátor mcservery.eu. Je nutné abyste vložili popis serveru a případně nastavili Votifier. K serveru se můžete dostat ze svého uživatelského profilu.

</details>

<details>

<summary>Kód jsem vložil do MOTD serveru ale převod stále nefunguje.</summary>

V popisu serveru nesmí být v momentě ověření přítomen žádný jiný text ani znaky než samotný kód.

Pokud tomu tak je, a server byl restartován je možné, že se změna MOTD ještě neprojevila v našem systému. Zkuste znovu stisknout tlačítko „Ověřit kód“ zhruba za 5 minut.

Pokud se nepodaří server převést ani do půl hodiny kontaktujte podporu na našem [Discordu](https://discord.mcservery.eu).

</details>

**Něco nám uniklo?**

Nebojte se! Rádi poradíme na [Discordu](https://discord.mcservery.eu) nebo [info@mcservery.eu](mailto:info@mcservery.eu) ✌️
