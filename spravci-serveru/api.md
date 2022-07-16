# API

## Co API umí?

* Zobrazení všech veřejně dostupných informací o serveru
* Seznam hráčů hlasujících pro server za posledních 30 dní
* Aktuální počet hlasů
* Status a další informace serveru (ip adresa, port, motd, verze, mód, hráči/sloty)

## Jak API používat?

#### **Získání klíče**

Pro používání api je nutné vygenerovat api key který vám zajistí přístup k informacím pro server se kterým je klíč navázaný. Klíč vygenerujete po přihlášení k účtu který je spojený s daným serverem. Je nutné být přihlášený na [http://mcservery.eu/login.php](http://mcservery.eu/login.php)

Pro vygenerování klíče si zobrazte seznam vašich serverů

![https://github.com/McServery/API-Dokumentace/raw/master/img/api1.JPG](https://github.com/McServery/API-Dokumentace/raw/master/img/api1.JPG)

Otevřete detail požadovaného serveru

![https://github.com/McServery/API-Dokumentace/raw/master/img/api2.jpg?raw=true](https://github.com/McServery/API-Dokumentace/raw/master/img/api2.jpg?raw=true)

Vygenerujte api klíč

![https://github.com/McServery/API-Dokumentace/raw/master/img/api3.JPG](https://github.com/McServery/API-Dokumentace/raw/master/img/api3.JPG)

Zkopírujte svůj api klíč

![https://github.com/McServery/API-Dokumentace/raw/master/img/api4.JPG](https://github.com/McServery/API-Dokumentace/raw/master/img/api4.JPG)

****

## Základní informace o serveru

{% swagger method="get" path="/?api_key=" baseUrl="http://api.mcservery.eu" summary="Informace o serveru" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="api_key" required="true" %}
Klíč pro daný server
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{ 
    "Name": "API Testovací server", "Description": "Testovací záznam pro zkoušku API", "Adress": "mc.hypixel.net", "Port": "25565", "Web": "http://api.mcservery.eu", "Discord": "", "Tag1": "", "Tag2": "", "Tag3": "", "Votes": "1", "VRD": "2020-08-25 15:39:03"
}
```

_VRD = Votes Reset Date - Hlasy se resetují jednou za 30 dní od přidání serveru, vždy při resetu se nastaví aktuální čas kdy byl reset proveden_
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Je vyžadován API key" %}
```javascript
{
    'code'    => 1,
    'message' => 'Je vyžadován API key, dokumentaci naleznete na: https://github.com/McServery/API-Dokumentace'
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="API key je neplatný" %}
```javascript
{   
    'code'    => 2,
    'message' => 'API key je neplatný'
}
```
{% endswagger-response %}
{% endswagger %}

## Hlasování

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

{% swagger-response status="400: Bad Request" description="Je vyžadován API key" %}
```javascript
{
    'code'    => 1,
    'message' => 'Je vyžadován API key, dokumentaci naleznete na: https://github.com/McServery/API-Dokumentace'
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="API key je neplatný" %}
```javascript
{
    'code'    => 2,
    'message' => 'API key je neplatný'
}
```
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

{% swagger-response status="400: Bad Request" description="Je vyžadován API key" %}
```javascript
{
    'code'    => 1,
    'message' => 'Je vyžadován API key, dokumentaci naleznete na: https://github.com/McServery/API-Dokumentace'
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="API key je neplatný" %}
```javascript
{
    'code'    => 2,
    'message' => 'API key je neplatný'
}
```
{% endswagger-response %}
{% endswagger %}

## Status serveru

{% swagger method="get" path="/status/?api_key=" baseUrl="http://api.mcservery.eu" summary="Status serveru" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="api_key" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Zobrazí aktuální status serveru" %}
****
{% endswagger-response %}

{% swagger-response status="200: OK" description="Server offline" %}
```javascript
{
    'code' => 3,
    'message' => 'Server offline'
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Je vyžadován API key" %}
```javascript
{
    'code' => 1, 
    'message' => 'Je vyžadován API key, dokumentaci naleznete na: https://github.com/McServery/API-Dokumentace'
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="API key je neplatný" %}
```javascript
{
    'code' => 2,
    'message' => 'API key je neplatný'
}
```
{% endswagger-response %}
{% endswagger %}

### ****

## Související články

{% content-ref url="pr-idani-noveho-serveru.md" %}
[pr-idani-noveho-serveru.md](pr-idani-noveho-serveru.md)
{% endcontent-ref %}

****

**Něco nám uniklo?**

Nebojte se! Stačí poslat e-mail. Rádi poradíme na [info@mcservery.eu](mailto:info@mcservery.eu) ✌️
