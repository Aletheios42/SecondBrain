**Tags:** #_Done
**MetaTags:** #Linux #Bash
- - -
# Expansión de llaves en Bash
La expansión de llaves es una técnica elegante para generar múltiples cadenas de texto de forma eficiente. 
### Listas de strings
Permite crear combinaciones de elementos individuales en una lista:  
```bash
echo {manzana,banana,cereza}
manzana banana cereza
```
### Secuencias numéricas
Genera secuencias de números consecutivos:
```bash
echo {1..5}
1 2 3 4 5
```
### Secuencias alfabéticas
Genera carpetas con letras alfabéticas para diferentes secciones:  
```bash
touch capítulo_{d..a}.md
ls capítulo_*
capítulo_d.md capítulo_c.md capítulo_b.md capítulo_a.md
```
### Ejemplo
Se pueden combinar listas, y las expende con el [[Producto Cartesiano]].
```bash
touch reporte_{ventas,ingresos}_{A..C}_{2021..2023}.txt
ls reporte_*
 reporte_ventas_A_2021.txt reporte_ventas_A_2022.txt reporte_ventas_A_2023.txt
 reporte_ingresos_C_2021.txt reporte_ingresos_C_2022.txt reporte_ingresos_C_2023.txt....
```
- - - 
## ***Sources:***