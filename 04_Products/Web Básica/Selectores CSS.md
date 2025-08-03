**MetaTags:** #_Todo
**Tags:** #CSS #ToLink 
- - -
### Básicos
- `* { }` → Selector universal, afecta todos los elementos.
- `p { }` → Selector de elemento, afecta todos los `<p>`.
- `.clase { }` → Selector de clase, afecta los elementos con esa clase.
- `#id { }` → Selector de ID, afecta un elemento con ese ID.
- `[type="text"] { }` → Selector de atributo, afecta elementos con ese atributo.
### Combinadores
- `div p { }` → Selector descendiente (todos los `<p>` dentro de `<div>`).
- `div > p { }` → Solo afecta a los hijos directos.
- `div + p { }` → Afecta el primer `<p>` inmediatamente después de `<div>`.
- `div ~ p { }` → Afecta todos los `<p>` que sean hermanos de `<div>`.
### Pseudo-clases
- `:hover` → Cuando el cursor está sobre el elemento.
- `:focus` → Cuando el elemento recibe foco.
- `:nth-child(n)` → Se aplica al n-ésimo hijo.
### Pseudo-elementos
- `::before` / `::after` → Insertan contenido antes o después del contenido del elemento.
- `::first-letter` → Afecta la primera letra.
- `::selection` → Afecta el texto seleccionado.

- - - 
## ***Sources:***