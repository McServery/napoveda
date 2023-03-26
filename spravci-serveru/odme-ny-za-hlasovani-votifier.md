# Odměny za hlasování (Votifier)

### Potřebné pluginy

nuVotifier a SuperbVote jsou pluginy který vám umožní odměnit hráče kteří hlasovali pro váš server.

Pro naslouchání příchozího komunikace je nutné nainstalovat na váš server plugin nuVotifier ([Spigotmc.org](https://www.spigotmc.org/resources/nuvotifier.13449/) / [GitHub](https://github.com/NuVotifier/NuVotifier))

nuVotifier kompatibilita:

* Bukkit / Spigot / Paper >=1.7.10
* Sponge 7
* BungeeCord / Waterfall
* Velocity

Pro odměňování hráčů je potřeba nainstalovat tzv. odměňovací plugin například [SuperbVote](https://www.spigotmc.org/resources/superbvote.11626/) nebo jakýkoliv jiný.

### Nastavení Votifieru

Po nainstalování Votifieru otevřete konfigurační soubor `plugins/votifier/config.yml` kde najdete port, ten změňte na jakýkoliv volný port který vám váš hosting umožňuje (Volné porty by měli být rozepsané v administraci vašeho hostingu). Po té zkopírujte váš public key z `plugins/votifier/rsa/public.key`. Public key a port vložte na server listu do příslušných polí.

Pokud jste vše nastavili správně měl by váš Minecraft server být schopný komunikovat s naším server listem.&#x20;

{% hint style="info" %}
Správné nastavení lze otestovat na tomto webu&#x20;

[https://mctools.org/votifier-tester](https://mctools.org/votifier-tester)
{% endhint %}

### Nastavení odměn

Nyní už zbývá jen nastavit plugin pro přidělování odměn hráčům kteří hlasovali pro váš server. Doporučujeme SuperbVote ([Spigotmc.org](https://www.spigotmc.org/resources/superbvote.11626/) / [GitHub](https://github.com/astei/SuperbVote))

Po instalaci SuperbVote si nastavte jaké odměny má hráč dostat za hlasování config naleznete ve složce `plugins/SuperbVote/config.yml`

### **Propojení s** [**Mcservery.eu**](https://mcservery.eu/)

**Pokud server ještě není přidaný** je možné Votifier propojit již při žádosti o přidání na server list.

**K propojení již přidaného serveru** stačí přejít na stránku serveru který chcete propojit (je nutné být přihlášen) a kliknout na tlačítko Votifier. K zprovoznění budete potřebovat dva údaje. Public key a volný port na kterém bude váš server komunikovat se server listem.

Pokud jste vše nakonfigurovali správně mělo by na stránce vašeho serveru být pole pro vyplnění nicku který má hlasující hráč na serveru. Nick vyplníte a pak už jen stačí hlas odeslat.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption><p>Pro propojení je nutné vyplnit public key a port</p></figcaption></figure>

## FAQs

<details>

<summary>Proč odměňovat hráče za hlasování?</summary>

Odměna za hlasování pro váš server motivuje hráče pravidelně hlasovat a tak zvyšovat viditelnost vašeho serveru na server listu.

</details>

## Související články

{% content-ref url="../serverlist/hlasovani.md" %}
[hlasovani.md](../serverlist/hlasovani.md)
{% endcontent-ref %}

****

**Něco nám uniklo?**

Nebojte se! Rádi poradíme na [Discordu](https://discord.mcservery.eu) nebo [info@mcservery.eu](mailto:info@mcservery.eu) ✌️
