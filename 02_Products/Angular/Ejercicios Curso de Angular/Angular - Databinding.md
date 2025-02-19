**Ejercicio 1: Property Binding con un botón deshabilitado dinámicamente**
### Enunciado
1. Define en tu componente una propiedad booleana que controle el estado de un botón.  
2. Usa *property binding* para el atributo `disabled` en la plantilla.  
3. Proporciona un botón que alterna el valor de la propiedad booleana, habilitando o deshabilitando el botón principal.

### Solución
**Componente (TypeScript)**  
```typescript
export class MiComponente {
  habilitado: boolean = false;

  alternarHabilitado() {
    this.habilitado = !this.habilitado;
  }
}
```

**Plantilla (HTML)**  
```html
<button (click)="alternarHabilitado()">Alternar estado</button>
<button [disabled]="!habilitado">Botón controlado</button>
<p>Estado del botón: {{ habilitado ? 'Habilitado' : 'Deshabilitado' }}</p>
```

---

**Ejercicio 2: Attribute Binding con `attr.aria-label`**
### Enunciado
1. Define en tu componente una propiedad que represente el texto de un atributo, por ejemplo: `valorAriaLabel`.  
2. Usa `attr.` para enlazar dinámicamente el atributo `aria-label`.  
3. Permite que el usuario cambie el valor a través de un campo de texto y observa cómo se actualiza el atributo.

### Solución
**Componente (TypeScript)**  
```typescript
export class MiComponente {
  valorAriaLabel: string = 'Botón inicial';
}
```

**Plantilla (HTML)**  
```html
<button [attr.aria-label]="valorAriaLabel">
  Botón con aria-label dinámico
</button>

<input
  type="text"
  [(ngModel)]="valorAriaLabel"
  placeholder="Cambia el aria-label"
/>
<p>aria-label actual: {{ valorAriaLabel }}</p>
```

Asegúrate de haber importado el `FormsModule` en tu `AppModule` para usar `[(ngModel)]`.

---

**Ejercicio 3: Class Binding y Style Binding**
### Enunciado
1. Crea dos propiedades en tu componente:  
   - `esResaltado` (tipo boolean) para alternar una clase CSS.  
   - `colorTexto` (tipo string) para cambiar dinámicamente el color de un texto.  
2. Usa `[class.nombreClase]="condicion"` para aplicar la clase cuando `esResaltado` sea `true`.  
3. Usa `[style.propiedad]="valor"` para asignar la propiedad `colorTexto` al estilo CSS.  
4. Proporciona controles (botón, `<select>`, etc.) para modificar ambas propiedades.

### Solución
**Componente (TypeScript)**  
```typescript
export class MiComponente {
  esResaltado: boolean = false;
  colorTexto: string = 'blue';

  alternarResaltado() {
    this.esResaltado = !this.esResaltado;
  }

  cambiarColor(nuevoColor: string) {
    this.colorTexto = nuevoColor;
  }
}
```

**Plantilla (HTML)**  
```html
<button (click)="alternarResaltado()">
  Alternar resaltado
</button>

<select (change)="cambiarColor($event.target.value)">
  <option value="blue">Azul</option>
  <option value="red">Rojo</option>
  <option value="green">Verde</option>
</select>

<p
  [class.resaltado]="esResaltado"
  [style.color]="colorTexto"
>
  Texto con binding de clase y estilo.
</p>
```

**Estilos (CSS)**  
```css
.resaltado {
  font-weight: bold;
  text-decoration: underline;
}
```
---
### Referencias y lecturas recomendadas
- [Documentación oficial de Angular: Data Binding](https://angular.io/guide/binding