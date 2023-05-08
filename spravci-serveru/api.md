---
description: >-
  Umožňuje komunikaci a výměnu dat. S rozhraním API můžete komunikovat
  prostřednictvím požadavků HTTP z libovolného jazyka.
---

# API

## Co API umí?

* Zobrazení všech veřejně dostupných informací o serveru
* Seznam hráčů hlasujících pro server za posledních 30 dní
* Aktuální počet hlasů
* Status a další informace serveru (ip adresa, port, motd, verze, mód, hráči/sloty)
* Detailní statistiky - https://mcservery.eu/stats

{% hint style="danger" %}
Nikomu nesdělujte ani neposílejte svůj API klíč. V případě vyzrazení vygenerujte nový – původní přestane být funkční.
{% endhint %}

## Jak API používat?

### **Získání klíče**

Pro používání api je nutné vygenerovat api key který vám zajistí přístup k informacím pro server se kterým je klíč navázaný. Klíč vygenerujete po přihlášení k účtu který je spojený s daným serverem. Je nutné být přihlášený na [http://mcservery.eu/login.php](http://mcservery.eu/login.php)

Pro vygenerování klíče si po přihlášení k Vašemu zobrazte detail Vámi přidaného serveru.&#x20;

Pod popisem serveru naleznete box s názvem „Upravit server“. Zde stačí kliknout na tlačítko vygenerovat api key.

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

### Rate limit

Rate limit je maximální počet API volání, které aplikace nebo uživatel může v určitém časovém období provést. Pokud je tento limit překročen, dojde k zablokování požadavků.

#### Proč limitujeme počty požadavků?

Je to běžnou praxí pro API a limity jsou zavedeny z několika důvodů:

* **Pomáhají chránit API proti zneužití nebo nesprávnému použití.** Například útočník by mohl zaplavit API požadavky v pokusu o přetížení serveru.
* **Limity pomáhají zajistit, že každý má spravedlivý přístup k API.** Pokud jedna osoba nebo aplikace provede nadměrný počet požadavků, mohlo by to zpomalit API pro všechny ostatní.

#### Jaké limity jsou nastaveny?

Maximum je **10 požadavků** během **10 vteřin.**

#### Co se stane pokud limit překročím?

Dojde k blokaci IP adresy ze které jsou požadavky odesílaný. **Blokace trvá 10 vteřin.**

Pokud narazíte na chybu **429** nebo **1015**, znamená to, že jste v krátkém časovém období provedli příliš mnoho požadavků a API odmítá plnit další požadavky, dokud neuplyne stanovené časové období.

**Stejné limity se vztahují i na přístup na web, tedy ne jen na API požadavky jako takové.**

## API reference

### Základní informace o serveru

### Hlasování

{% swagger method="get" path="/players/?api_key=" baseUrl="http://api.mcservery.eu" summary="Hlasující hráči za posledních 30 dní" %}
{% swagger-description %}
Zobrazí jednotlivé hlasy podle uživatelského jména a času kdy byl hlas udělen.
{% endswagger-description %}

{% swagger-parameter in="query" name="api_key" required="true" %}
Klíč pro daný server
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{ 
  "username": "ArtyomCZ", "time": "2020-08-25 18:38:00"
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Code 1: Je vyžadován API key" %}
```javascript
{
    'code'    => 1,
    'message' => 'Je vyžadován API key, dokumentaci naleznete na: https://github.com/McServery/API-Dokumentace'
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Code 2: API key je neplatný" %}
```javascript
{
    'code'    => 2,
    'message' => 'API key je neplatný'
}
```
{% endswagger-response %}

{% swagger-response status="429: Too Many Requests" description="Rate limit" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/votes/?api_key=" baseUrl="http://api.mcservery.eu" summary="Počet hlasů" %}
{% swagger-description %}
Zobrazí počet hlasů pro daný server.
{% endswagger-description %}

{% swagger-parameter in="query" name="api_key" required="true" %}
Klíč pro daný server
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "Votes": "1"
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Code 1: Je vyžadován API key" %}
```javascript
{
    'code'    => 1,
    'message' => 'Je vyžadován API key, dokumentaci naleznete na: https://github.com/McServery/API-Dokumentace'
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Code 2: API key je neplatný" %}
```javascript
{
    'code'    => 2,
    'message' => 'API key je neplatný'
}
```
{% endswagger-response %}

{% swagger-response status="429: Too Many Requests" description="Rate limit" %}

{% endswagger-response %}
{% endswagger %}

{% embed url="https://mcservery.eu/blog/mcservery-api-zebricek-hlasujicich-pro-vas-server/" %}
Pomocí endpointu /players/ lze vytvořit žebříček hlasujících pro Váš server.
{% endembed %}

### Status serveru

{% swagger method="get" path="/status/?api_key=" baseUrl="http://api.mcservery.eu" summary="Status serveru" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="api_key" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Zobrazí aktuální status serveru" %}

{% endswagger-response %}

{% swagger-response status="200: OK" description="Code 3: Server offline" %}
```javascript
{
    'code' => 3,
    'message' => 'Server offline'
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Code 2: API key je neplatný" %}
```javascript
{
    'code' => 2,
    'message' => 'API key je neplatný'
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Code 1: Je vyžadován API key" %}
```javascript
{
    'code' => 1, 
    'message' => 'Je vyžadován API key, dokumentaci naleznete na: https://github.com/McServery/API-Dokumentace'
}
```
{% endswagger-response %}

{% swagger-response status="429: Too Many Requests" description="Rate limit" %}

{% endswagger-response %}
{% endswagger %}



## Související články

{% content-ref url="pr-idani-noveho-serveru.md" %}
[pr-idani-noveho-serveru.md](pr-idani-noveho-serveru.md)
{% endcontent-ref %}



**Něco nám uniklo?**

Nebojte se! Rádi poradíme na [Discordu](https://discord.mcservery.eu) nebo [info@mcservery.eu](mailto:info@mcservery.eu) ✌️
