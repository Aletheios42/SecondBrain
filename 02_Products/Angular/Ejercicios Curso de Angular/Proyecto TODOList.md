**Tags:** #_Todo
#ToTag #ToLink 
- - -
# Instalar
ahora fijate que el main te da error. asi que tienes que instalar las dependencias listasdas en el packjson con:
```  
npm install
```
para visualizar la web que estas desarrollando hacer el comando:
``` 
npm start
```
que llama a ng serve

#  Intro
Explicar como index.html llama al main.ts que importa un componente guardado en app
que a su vez a traves de un decorador importa el elemento html y sus stilos
leer el codigo para hacer el seguimiento e instacionar el codigo fuente de la pagina de bienvenida de angular
# Componente  Header
hacer a mano el componente header y explicar como se importan y exportan, y como estos pasan a ser accesibles en los htmls de componente
# Hacer a mano el Componente User
Hacer el componente user desde el cli
y hacer la barrita sin foto todavia, importando el array
# Hacer Dinamico el componente User
 A traves de binding ya sea con los corhcetes o con la doble llame. linkea la imagen randowm con la barra.
# Utilizar getters 
cambia el atribute binding por un getter para coger la imagen, ademas aplica un evento on click en el  user*.html para cargar la imagen desde un getter de la clase
# State: Actualizar UX por eventos sec2.26
crear un nuevo "onSelectUser" para que cuando cada vez que cliceo ... pues se cambie de nombre
# Signals
sustituir lo hecho con eventos con señales, el id con signal() y el getter con computed()
en el getter se forma una estructura muy efeciente cuando haces un signals dentro deun computed pues, solo se cambia el computed si cambia la señal del input, y cmo esta genera una suscriptcion actualiza el UX
 y recordar actualizar el html del componente user, con los parentesis de las señales
# componentes reutilizables para formar una lista de usuarios
asi que rehago otra vez el componente user para ser reutilizable con @Input(), y como no lo vasmos a asignar de manea programatica, podemos permitirnos declararlo con !, y luego dereferenciar , en el html de app-component en form a de lista, y quitar los parentesis de las señales del user.html (pero no el del clicl que eso es un evento)
# Hacer que los decoradores de Input sea required
hacer una demo borrando uno de los 4 nombres, e introducir que el required
# Input + signals
explicar como inpunt()  funciona y su flexibilidad de tipos con \<>(typescript generic type) y poner lo del defualt value, nombrar el atributo .required, y sustituir los decoradores por input(), asi que en user.html, hayq ue poner a name y avatar otra vez los parentesis pues vuelven  a ser señales

# Output property para eventos sec2 34
Dejarlo como estado otra vez, con decorador input, y añadir decorador output en el users.ts
y añadir el campo id a los usuarios, y emitir evento

- - - 
## ***Sources:***