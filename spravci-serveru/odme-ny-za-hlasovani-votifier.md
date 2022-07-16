# Odměny za hlasování (Votifier)

**Nastavení pluginů**

Votifier je plugin který vám umožní odměnit hráče kteří hlasovali pro váš server.

Pro naslouchání příchozího komunikace je nutné nainstalovat na váš server plugin nuVotifier ([Spigotmc.org](https://www.spigotmc.org/resources/nuvotifier.13449/) / [GitHub](https://github.com/NuVotifier/NuVotifier))

nuVotifier kompatibilita:

* Bukkit / Spigot / Paper >=1.7.10
* Sponge 7
* BungeeCord / Waterfall
* Velocity

Po nainstalování votifieru otevřete konfigurační soubor `plugins/Votifier/config.yml`kde najdete port, ten změňte na jakýkoliv volný port který vám váš hosting umožňuje (Volné porty by měli být rozepsané v administraci vašeho hostingu). Po té zkopírujte váš public key z `plugins/Votifier/rsa/public.key`. Public key a port musíte vložit při úpravě serveru na server listu.

Pokud jste vše nastavili správně měl by váš Minecraft server být schopný komunikovat s naším server listem. Nyní už zbývá jen nastavit plugin pro přidělování odměn hráčům kteří hlasovali pro váš server. Doporučujeme superbvote ([Spigotmc.org](https://www.spigotmc.org/resources/superbvote.11626/) / [GitHub](https://github.com/astei/SuperbVote))

Po instalaci superbvote si nastavte jaké odměny má hráč dostat za hlasování config naleznete ve složce `plugins/SuperbVote/config.yml`

{% hint style="info" %}
Správné nastavení lze otestovat na tomto webu&#x20;

[https://mctools.org/votifier-tester](https://mctools.org/votifier-tester)
{% endhint %}

### **Propojení s** [**Mcservery.eu**](https://mcservery.eu/)

**Pokud server ještě není přidaný** je možné Votifier propojit již při žádosti o přidání na server list.

**K propojení již přidaného serveru** stačí přejít na stránku serveru který chcete propojit a kliknout na tlačítko votifier. K zprovoznění budete potřebovat dva údaje. Public key a volný port na kterém bude váš server komunikovat se server listem.

Pokud jste vše nakonfigurovali správně mělo by na stránce vašeho serveru být pole pro vyplnění nicku který má hlasující hráč na serveru. Nick vyplníte a pak už jen stačí hlas odeslat.

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

Nebojte se! Stačí poslat e-mail. Rádi poradíme na [info@mcservery.eu](mailto:info@mcservery.eu) ✌️
