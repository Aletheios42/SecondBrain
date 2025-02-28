
































===================================================
# Paso 0. Crea el proyecto y copia assets y dummy-users.ts

# Paso 1: Componente  Header
- copia los estilos
- en el html, haz un header que cargue la imagen del logo y tenga un encabezado
- exporta la clase y usa el selector en app.component
# Paso2: Crea User I
- crea el componente user
-  importa el array de dummy-user y asigna una propieda "selectedUser" a objeto \[0].
- constuye el html con img y span envueltos en un boton envuelto en un div
-  muuestra su numbre con string interpotalion en el html. 
-  muuestra su avatar con string interpotalion en el html. 
- Importa user a app..component y usar su selctor. 
interesante asignar un indice dinamico, escribe esto justo debajo de los imports
``` ts
const random_index = math.floor(math.random() * DUMMY_USERS.lenght)
```
mira local host y recarga, deberias ver como cambian los nombres aleatorioamente y la imagen deberia NO cargar correctamente
# Paso3: Crea User Property binding
- bienda alt a selectedUser.name

- computar el path assest/user + selectedUser.avatar de 2 maneras
	- una funcion que retorne el path computado \[src]="imagePath()"
	- un metodo get  --->  \[src]="imagepath"
ahora deberias volver a mirar local host y deberia funcionar la imagen y recargarse
computar el path assest/user + selectedUser.avatar de 2 maneras

# Paso3: User Escuchando Eventos
- crea una funcion onSelectUser() que haga un muestre un mensaje por pantalla1
- añade un evento (click) al boton  y asignalo al metodo de arriba
mira la consola en localhost, deberias ver el mensaje

ahora vamos a aprender a juntar lo aprendeido para cambiar el UX cuando el usuario click por pantalla gracias a eventos (click)

mete la constante en el metodo onSelectUser() y asignala : "this.selectedUser"
para que cada vez que se click el component se llame a onSelectUser() se compute nuevamente un valor automatico
# Paso 4 User Señales
https://angular.dev/guide/signals

comenta tu getter:
``` ts
  // get imagePath() {
  //   return 'assets/users/' + this.user.avatar;
  // }
}
```
-  cambia selected user para usar signal()
```ts
selectedUser = signal(DUMMY_USERS[randomIndex])
```
- genera la imagen con computed(), ahora como selectedUser es una señal para leerlo, y tratarlo como un string hay que usar selectedUser()
``` ts
imagePath = computed(()=> 'assest/user/' + this.selectedUser().avatar)
```
usa el metodo .set() en onSelect()
comprueba localhost, deberia funcional exactamente igual que antes

# Paso 5: custom Compoent
Us el selector app-user varias veces en app.componet.html y mira localhost.

todos son iguales, por lo que esta arquitectura de app no nos vale para renderizar usuarios disintos, asi que vamos limpiar todo user.app.component.ts  dejando el metedo onSelectUser() {} 

- añade las propiedades avatar con el decorardor @Input() avatar:string;
- en app.compoent.ts asigna la propiedad users a DUMMY_USER e importalo
- haz propertybinding en app.componet.html con \<app-user \[avatar]="user\[0]"
- repite el paso anterior con los 6 usuarios

deberias ver un probelma en avatar ya que no esta inicializado, asi que añade  ! ,
ya que avatar sera asignado en el scoope de app.component a traves de databinding, pero eso angular no lo sabe.

reescribe el get comentado arriba,  y haz lo mismo que hemos hecho con avatar, es decir declararlo con dataInputProperty  y bindearlo en app.componet
cambia el html de usercompoent para adaptar la nueva propiedad name

ahora mira localhost deberias ver los usuarios renderizados correctamente
# Paso 6: test
borra uno de los data banding de app.component.html por ejemplo un nameTest
- mira localhost, funciona pero falta el nombre que has borrado 
- asi que vamos a usar required en @Input()   mirar docs
- volver a escribir el name borrado
# Paso 7: usa señales(opcional)
- cambia @Input()  por input()
- recuerda porner el tipo correctamente
- recuerda leer las funciones correctamente() , solo en el componente donde se declara la señal, en app.component es irrelevante.

vuelve a dejarlo todo com al final del paso 6

# Paso 8: custom events
queremos hacer que cuando clicamos aparezca un dashboard, asi que tenemos que mandar nu evento desde el componente user a app.component para que este gestione el renderizado del nuevo dashboard
añade en user.component.ts
``` ts
@Input({ required: true }) id!: id;
@Output() select  = new EventEmitter();
onSelectUser(){
this.select.emit(this.id);
}
```
- bindea \[id] en app.compoent
- bindea (select), recuerda la variable $event
- añade un metodo onSelectUser(id: string) {console.log("selected user with id + id")}

mira local host deberias ver el usuario que selecinas por consola

# Paso 9
- hacer el @Output() con la señal output()
- dejarlo com estaba en el paso 8
# Paso 10 
 crea un componente llamado tasks que enseñe las tareas de cada usuario por pantalla
 - crea el componente e importalo a app component
 - haz que reciba el nombre del usuario seleccionado
 - enseñalo con string interpolation por el html
 pista: puesdes encontrar un id especifio en el array con esta linea:
 DUMMY_USERS.find(user => user.id == selectedUserId)!