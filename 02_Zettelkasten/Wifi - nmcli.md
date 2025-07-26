**MetaTags:** #_Done 
**Tags:** #Redes  #nmcli #Wifi #Linux
- - -
Este procedimiento detalla cómo conectarte a la red Wi-Fi "Eventos" usando `nmcli`.
### 1. Eliminar configuraciones previas

Si ya existe una configuración para la red "Eventos", elimínala para evitar conflictos:
```bash
nmcli connection delete "Eventos"
```
**`nmcli connection delete:`**  Borra una conexión previamente configurada.
**`"Eventos":`** Nombre de la conexión a eliminar.
### 2. Crear una nueva conexión
Usa el siguiente comando para configurar la red Wi-Fi con su clave:

```bash
nmcli connection add type wifi con-name "Eventos" ifname wlan0 ssid "Eventos" wifi-sec.key-mgmt wpa-psk wifi-sec.psk "42Madrid"
```
- **`nmcli connection add`**: Crea una nueva conexión.
- **`type wifi`**: Especifica que la conexión es de tipo Wi-Fi.
- **`con-name "Eventos"`**: Nombre personalizado para la conexión.
- **`ifname wlan0`**: Nombre de la interfaz Wi-Fi (puedes usar `*` si no estás seguro del nombre exacto).
- **`ssid "Eventos"`**: Identificador de la red Wi-Fi.
- **`wifi-sec.key-mgmt wpa-psk`**: Método de gestión de claves (WPA con clave precompartida).
- **`wifi-sec.psk "42Madrid"`**: Clave de acceso para la red.`
### 3. Activar la conexión
Después de crear la conexión, actívala con:

```bash
nmcli connection up "Eventos"
```

**`nmcli connection up:`** Activa la conexión especificada.
**`"Eventos"`**: Nombre de la conexión a activar.
### 4. Verificar conexiones activas

Confirma que estás conectado verificando las conexiones activas:
```bash
nmcli connection show --active
```
### Alternativa: Uso de comodín para la interfaz
Si no estás seguro del nombre de tu interfaz Wi-Fi, puedes usar * en lugar de wlan0:

```bash
nmcli connection add type wifi con-name "Eventos" ifname "*" ssid "Eventos" wifi-sec.key-mgmt wpa-psk wifi-sec.psk "42Madrid"
```
ifname "\*": Indica que se debe usar cualquier interfaz Wi-Fi disponible.
- - - 
#### ***Sources:***