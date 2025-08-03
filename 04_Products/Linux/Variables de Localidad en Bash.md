**MetaTags:** #_Done 
**Tags:** #Linux #Bash 
- - -
Controlan el idioma, formato de fechas, moneda, orden de clasificación, etc.  

- **Cómo listarlas**:  
  ```bash
  locale
  ```

- **Ejemplos típicos de variables de localización:**
  - `LANG` (idioma y codificación predeterminada, ej. `es_ES.UTF-8`)
  - `LC_ALL` (fuerza todas las configuraciones regionales a un mismo valor)
  - `LC_TIME` (controla el formato de fecha y hora)
  - `LC_MONETARY` (controla la moneda predeterminada)

	`env` y `printenv` también las mostrarán estas variables.
- - - 
## ***Sources:***