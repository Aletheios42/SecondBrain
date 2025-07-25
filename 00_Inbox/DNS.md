**MetaTags:** #_Todo
**Tags:** #ToTag #ToLink 
- - -

Es un sistema distribuido y jerarquizado diseñado para resolver nombres como www.aletheia.xyz en direcciones ip y otros registros asociados.


Organizada en niveles:

Root (.)

Top-Level Domains (TLD): .com, .org, .net, .edu, etc.

Second-Level Domains: example.com

Subdominios: www.example.com

esta gestionado por 2 grandes instituciones:
ICANN (Internet Corporation for Assigned Names and Numbers):

Supervisa el sistema de nombres y números de Internet.

Acredita registradores de dominios.

Define políticas globales sobre nombres de dominio.

IANA (Internet Assigned Numbers Authority):

Mantenida por ICANN.

Administra la zona raíz del DNS, direcciones IP, y parámetros de protocolo.

#### Proceso de busqueda recursiva
[Cliente] → [Recursor local]
           ↳ [Servidor raíz]
               ↳ [Servidor TLD]
                   ↳ [Servidor autoritativo]
                       → [Respuesta al recursor]
           ← [Respuesta al cliente]


DNS recors:
- A record: mapea hostnames con ipv4
- AAAA record: mapea hostnames con ipv6
- CNAME: mapea alias a hostnames
- PTR Records: pointer record to canonical naes
- MX record: mapea los main servers a un dominio especifico, definiendo un camino
- - - 
#### ***Sources:***