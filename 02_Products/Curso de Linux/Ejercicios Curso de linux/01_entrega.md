**Tags:** #_Todo
#ToTag #ToLink 
- - -
# Operaciones del Sistema de Archivos y Procesamiento de Texto en Linux

## Navegación del Sistema de Archivos
### Comandos de Ubicación
- `pwd`: Muestra el directorio de trabajo actual. Devuelve la ruta absoluta desde la raíz.
- `cd`: Navegación entre directorios. Usos notables:
  - `cd -`: Cambiar al directorio anterior
  - `cd ~`: Navegar al directorio home
  - `cd ..`: Subir un nivel
  - `cd /ruta/absoluta`: Navegar usando ruta absoluta

### Información de Directorios
- `ls`: Listar contenido del directorio. Opciones principales:
  - `-l`: Formato largo con permisos, propietario, tamaño, fecha
  - `-a`: Mostrar archivos ocultos (que comienzan con .)
  - `-h`: Tamaños legibles para humanos
  - `-R`: Listado recursivo
  - `-d`: Listar los directorios en sí, no su contenido
  - `-i`: Mostrar números de inodo

## Manipulación del Sistema de Archivos
### Creación de Archivos y Enlaces
- `mkdir`: Crear directorios
  - `-p`: Crear directorios padre según sea necesario

- `touch`: Crear/actualizar marcas de tiempo de archivos
  - `-t`: Establecer tiempo específico [[CC]YY]MMDDhhmm[.ss]

- `ln`: Crear enlaces entre archivos
  - Enlaces duros: `ln origen destino`
  - Enlaces simbólicos: `ln -s origen destino`
  - Diferencia clave: Enlaces duros comparten inodo, enlaces simbólicos referencian ruta

## Información del Sistema
### Sistema y Usuario
- `uname`: Muestra información del sistema
  - `-a`: Toda la información
  - `-v`: Versión del kernel

- `whoami`: Muestra el nombre del usuario actual
- `whereis`: Localiza archivos binarios, fuente y manuales
- `whatis`: Muestra descripciones de una línea del manual
- `which`: Localiza el ejecutable de un comando
- `date`: Muestra o establece fecha y hora del sistema
- `cal`: Muestra calendario
- `bc`: Calculadora en línea de comandos

### Historial de Comandos
- `history`: Muestra historial de comandos
- `!`: Expansión del historial
  - `!!`: Ejecuta último comando
  - `!n`: Ejecuta comando número n

## Procesamiento de Texto
### Visualización y Manipulación de Archivos
- `cat`: Concatena y muestra archivos
  - `-n`: Numera todas las líneas
  - `-b`: Numera líneas no vacías
  - `-s`: Suprime líneas vacías repetidas

- `less`: Ver contenido con paginación
  - `/patrón`: Buscar hacia adelante
  - `?patrón`: Buscar hacia atrás
  - `n`: Siguiente coincidencia
  - `N`: Coincidencia anterior

- `head`: Mostrar primeras líneas
  - `-n N`: Mostrar primeras N líneas
  - `-c N`: Mostrar primeros N bytes

- `tail`: Mostrar últimas líneas
  - `-n N`: Mostrar últimas N líneas
  - `-F`: Seguir y reintentar si el archivo es inaccesible

- `wc`: Cuenta palabras, líneas, caracteres y bytes
  - `-l`: Solo líneas
  - `-w`: Solo palabras
  - `-c`: Solo bytes
  - `-m`: Solo caracteres

### Transformación de Texto
- `tr`: Traduce o elimina caracteres
  - `tr 'conjunto1' 'conjunto2'`: Reemplaza caracteres
  - `-d`: Elimina caracteres
  - `-s`: Comprime caracteres repetidos

- `sed`: Editor de flujo para filtrar y transformar texto
  - `s/patrón/reemplazo/`: Sustituye texto
  - `d`: Elimina líneas
  - `-i`: Edita archivos in situ
  - `p`: Imprime espacio de patrón

- `grep`: Búsqueda de patrones en archivos
  - `-i`: No distinguir mayúsculas y minúsculas
  - `-v`: Invertir coincidencia
  - `-r`: Búsqueda recursiva
  - `-n`: Mostrar números de línea
  - `-E`: Regex extendido

## Redirecciones
- `<`: Redirige la entrada estándar (stdin) desde un archivo
- `<<<`: Here string: redirige un string como entrada
- `<<EOF`: Here document: permite introducir múltiples líneas de entrada
- `>`: Redirige la salida estándar (stdout) a un archivo, sobrescribiéndolo
- `>>`: Redirige la salida estándar (stdout) a un archivo, agregando al final
- `<&`: Duplica descriptores de archivo para entrada
- `>&`: Duplica descriptores de archivo para salida

## Acceso a Documentación
- `man`: Páginas del manual
  - Secciones: 1 (comandos), 2 (llamadas al sistema), 3 (funciones de biblioteca)
  - `man -k palabra_clave`: Buscar en páginas del manual
  - `man -f comando`: Mostrar todas las páginas disponibles

- `info`: Documentación GNU
  - Más detallada que las páginas man
  - Formato hipertexto
  - Navegación: n (siguiente), p (anterior), u (arriba)

- `--help`: Referencia rápida de comandos
  - Disponible para la mayoría de utilidades GNU
  - Muestra opciones comunes y usok

- - - 
## ***Sources:***