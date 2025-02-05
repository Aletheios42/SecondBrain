**Tags:** #_Todo
#ToTag #ToLink 
- - -

buscar por frecuencias
buscar un patron con numero
buscar un patron con letra

Preparación: Descargar el texto de El Señor de los Anillos
Descarga un libro similar, como The Fellowship of the Ring, de Project Gutenberg:

wget https://www.gutenberg.org/cache/epub/36201/pg36201.txt -O lotr.txt
Trabajaremos con el archivo lotr.txt. Si no puedes descargarlo, usa otro texto largo disponible.

Ejercicios Avanzados con Regex
1. Buscar palabras con una letra específica repetida varias veces
Encuentra todas las líneas donde una letra se repita al menos 3 veces consecutivamente, como ooo o aaa.
grep -E "(.)\1{2,}" lotr.txt
2. Identificar palabras largas
Encuentra todas las líneas que contengan palabras con al menos 10 caracteres.
grep -E "\b[a-zA-Z]{10,}\b" lotr.txt
3. Búsqueda de palabras que comiencen y terminen con la misma letra
Encuentra líneas que contengan palabras como deified o radar.
grep -E "\b([a-zA-Z])([a-zA-Z]*)\1\b" lotr.txt
4. Buscar oraciones que terminen en signos de interrogación o exclamación
Encuentra todas las líneas que terminen con ? o !.
grep -E "[?!.]$" lotr.txt
5. Buscar líneas que contengan dos palabras consecutivas iguales
Encuentra líneas con repeticiones como the the o and and.
grep -E "\b([a-zA-Z]+) \1\b" lotr.txt
6. Buscar fechas en formato común
Encuentra líneas que contengan fechas como 01/01/2025 o 2025-01-01.
grep -E "\b([0-9]{4}-[0-9]{2}-[0-9]{2}|[0-9]{2}/[0-9]{2}/[0-9]{4})\b" lotr.txt
7. Identificar números con formato especial
Encuentra líneas que contengan números con separadores de miles, como 1,000 o 2,500,000.
grep -E "\b[0-9]{1,3}(,[0-9]{3})+\b" lotr.txt
8. Buscar líneas con una estructura de diálogo
Encuentra líneas que comiencen con un guion largo (—) seguido de texto (diálogos).
grep -E "^—" lotr.txt
9. Buscar acrónimos
Encuentra líneas que contengan acrónimos como FBI o NASA (palabras en mayúsculas de al menos 2 letras).
grep -E "\b[A-Z]{2,}\b" lotr.txt
10. Buscar palabras con combinaciones de vocales y consonantes
Encuentra palabras que alternen vocales y consonantes, como banana.
bash
Copy
Edit
grep -E "\b([aeiou][^aeiou])+\b" lotr.txt
Ejercicios de Contexto
11. Obtener líneas con contexto adicional
Busca líneas que contengan la palabra ring y muestra 2 líneas de contexto antes y después.
bash
Copy
Edit
grep -C 2 "ring" lotr.txt
12. Buscar párrafos completos con patrones
Encuentra párrafos enteros que contengan la palabra Gandalf.
bash
Copy
Edit
grep -zoE "(.*\n){0,2}Gandalf(.*\n){0,2}" lotr.txt
13. Buscar y contar palabras únicas
Encuentra todas las palabras únicas que empiezan con Frodo.
grep -oE "\bFrodo[a-zA-Z]*\b" lotr.txt | sort | uniq
14. Buscar combinaciones de palabras específicas
Encuentra líneas que contengan tanto Frodo como Sam en cualquier orden.
grep -E "(Frodo.*Sam|Sam.*Frodo)" lotr.txt

Desafío Final
Crea tus propias expresiones regulares para resolver los siguientes problemas:

Encuentra líneas que contengan números romanos (como XIV, III o MCMXC).
Encuentra nombres propios que comiencen con mayúsculas y tengan al menos 6 letras.
Busca frases que contengan exactamente 5 palabras.


- - - 
## ***Sources:***