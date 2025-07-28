**MetaTags:** #_Todo
**Tags:** #Docker #Devops 
- - -
Las imagenes de docker son **urls**:

$$
  \Large
  \underbrace{\textcolor{blue}{\text{docker.io}}}_{\textcolor{blue}{\text{Dominio}}} \texttt{/}
  \underbrace{\textcolor{teal}{\text{library}}}_{\textcolor{teal}{\text{Ruta}}} \texttt{/}
  \underbrace{\textcolor{orange}{\text{nginx}}}_{\textcolor{orange}{\text{Tag}}}
  \underbrace{\textcolor{red}{\text{:1.25}}}_{\textcolor{red}{\text{Digest}}}
$$

| Componente  | Descripción                                           | Ejemplo             | Valor por defecto |
| ----------- | ----------------------------------------------------- | ------------------- | ----------------- |
| `registro`  | Servidor de imágenes (opcional)                       | `docker.io`         | `docker.io`       |
| `namespace` | Agrupador lógico (usuario, organización, o `library`) | `library`, `myuser` | `library`         |
| `nombre`    | Nombre de la imagen (obligatorio)                     | `nginx`, `ubuntu`   | —                 |
| `tag`       | Etiqueta de versión (opcional)                        | `:1.25`, `:latest`  | `:latest`         |

#### Notas importantes
- Si omites registro, se asume docker.io.
- Si omites namespace, se asume library.
- Si omites tag, se usa latest.
- - - 
#### ***Sources:***
