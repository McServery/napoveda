# Doména serveru

Aby se hráč mohl připojit k vašemu Minecraft serveru, musí mít adresu vašeho serveru, kterou zadá pro připojení se na server.

Ve výchozím nastavení vypadá adresa serveru asi takto: 192.168.1.2:25565, ale to může být matoucí. Snadný způsob, jak mít adresu serveru, kterou si snadno zapamatujete, je použít doménu (např. mcservery.eu) nebo subdoménu (např. play.mcservery.eu).

Toto nám umožní DNS záznamy u vaší zakoupené domény.

## DNS záznamy

Je potřeba vytvořit dva DNS záznamy.

{% hint style="warning" %}
Než se projeví změna DNS záznamů může to trvat až 1 hodinu, nebo i více.
{% endhint %}

### 1. Záznam typu A

|        | Vlastní doména                                 | Vlastní subdoména                                                |
| ------ | ---------------------------------------------- | ---------------------------------------------------------------- |
| Typ    | A                                              | A                                                                |
| Název  | @ nebo mservery.eu                             | play.mcservery.eu Play může být nahrazeno jakoukoliv subdoménou. |
| TTL    | 3600                                           | 3600                                                             |
| Adresa | IP vašeho serveru bez portu, např. 192.168.2.1 | IP vašeho serveru bez portu, např. 192.168.2.1                   |

### 2. Záznam typu SRV

|                  | Vlastní doména                                                               | Vlastní subdoména                                                                  |
| ---------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Typ              | SRV                                                                          | SRV                                                                                |
| Název            | \_minecraft.\_tcp.mcservery.eu                                               | \_minecraft.\_tcp.play.mcservery.eu Play může být nahrazeno jakoukoliv subdoménou. |
| TTL              | 3600                                                                         | 3600                                                                               |
| Priorita & Váha  | 0                                                                            | 0                                                                                  |
| Port             | Port vašeho serveru (Např: 25565).                                           | Port vašeho serveru (Např: 25565).                                                 |
| Cíl              | @                                                                            |                                                                                    |
|  or mcservery.eu | play.mcservery.eu Nahraďte subdoménou, kterou jste zadali u svého záznamu A. |                                                                                    |

## Související články

{% content-ref url="../spravci-serveru/pr-idani-noveho-serveru.md" %}
[pr-idani-noveho-serveru.md](../spravci-serveru/pr-idani-noveho-serveru.md)
{% endcontent-ref %}



**Něco nám uniklo?**

Nebojte se! Rádi poradíme na [Discordu](https://discord.mcservery.eu) nebo [info@mcservery.eu](mailto:info@mcservery.eu) ✌️
