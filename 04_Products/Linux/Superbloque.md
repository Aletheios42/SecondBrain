**MetaTags:** #_Done 
**Tags:** #Linux 
- - -
Estructura maestra que mantiene el estado y la configuración del sistema de archivos. Almacena la información fundamental para la gestión y montaje del sistema de archivos:
- Dimensiones: tamaño total, tamaño de bloque, número total de entradas en la [[Tabla de Inodos]].
- Gestión de recursos: mapa de bloques disponibles y registro de inodos no asignados
- Estado: flags de montaje, último montaje, última verificación
- Identificación: tipo de sistema de archivos, etiqueta, UUID

El sistema mantiene múltiples copias como mecanismo de recuperación ante fallos.

- - - 
## ***Sources:***