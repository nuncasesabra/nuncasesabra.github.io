# Guía de la web

Esta carpeta es tu web completa. Se aloja gratis en GitHub Pages y para usarla no hace falta instalar nada ni saber programar: todo se hace desde el navegador.

---

## 1. Ponerla en internet (una sola vez, unos 15 minutos)

1. **Crea una cuenta en [github.com](https://github.com).** El nombre de usuario que elijas formará parte de la dirección de la web hasta que tengas dominio propio (`tu-usuario.github.io`).

2. **Crea un repositorio.** Arriba a la derecha, botón **+** → *New repository*.
   - En *Repository name* escribe exactamente: `tu-usuario.github.io` (con tu usuario).
   - Déjalo en **Public**.
   - Pulsa *Create repository*.

3. **Sube los archivos.** En la página del repositorio recién creado, pulsa el enlace *uploading an existing file*. Descomprime el zip en tu ordenador, abre la carpeta y arrastra **todo lo que hay dentro** (las carpetas `_layouts`, `_includes`, `_posts`, `assets` y el resto de archivos) a la ventana del navegador. Abajo, pulsa *Commit changes*.

4. **Activa la web.** En el repositorio: *Settings* → *Pages* (en el menú de la izquierda). En *Source* elige *Deploy from a branch*; en *Branch*, `main` y `/ (root)`. Guarda.

5. Espera uno o dos minutos y entra en `https://tu-usuario.github.io`. Ya está.

6. **Ajusta tus datos.** Abre el archivo `_config.yml` en GitHub, pulsa el lápiz (✏️) y cambia:
   - `url:` → `https://tu-usuario.github.io`
   - `substack:` → la dirección de tu Substack
   - `lema:` → la frase de la portada (o déjala vacía con `""`)
   - `correo:` y `letterboxd:` si quieres que aparezcan al pie

   Pulsa *Commit changes*. Revisa también `sobre-mi.md`: es un borrador para que lo reescribas.

---

## 2. Publicar un texto nuevo

1. En GitHub, entra en la carpeta **`_posts`**.
2. *Add file* → *Create new file*.
3. Ponle de nombre la fecha y el título, sin tildes ni espacios:
   `2026-11-20-aprender-a-vivir-por-fin.md`
   (la fecha es la que aparecerá publicada).
4. Copia el contenido de `plantilla-texto-nuevo.md`, pégalo y rellena la cabecera:

   ```
   ---
   title: Aprender a vivir por fin
   subtitulo: ""
   categoria: ensayos
   resumen: Sobre el duelo y la cohabitación con los fantasmas.
   substack: ""
   ---
   ```

   - `categoria`: `ensayos` o `academico`.
   - `subtitulo` y `substack` son opcionales: si no los usas, déjalos como `""`.
   - `imagen`: opcional. Mira el apartado «Imágenes en el margen» justo debajo.
   - Si el título o el resumen llevan dos puntos (:), ponlos entre comillas: `title: "Tabakladen: Celan lee a Campos"`.

5. Debajo de la segunda línea de guiones, pega el texto.
6. *Commit changes*. En un par de minutos aparece en la web.

### Imágenes en el margen

Cada texto puede llevar una imagen en el margen izquierdo, junto a la fecha. Aparece en la portada y en la página del texto (en el móvil, encima).

1. En GitHub, entra en la carpeta `assets/img` → *Add file* → *Upload files*, arrastra la foto y pulsa *Commit changes*. Usa nombres sin tildes ni espacios: `muro-eur.jpg`.
2. En la cabecera del texto, rellena:
   ```
   imagen: /assets/img/muro-eur.jpg
   imagen_texto: Un muro blanco con una sombra en diagonal
   imagen_pie: ""
   ```
   `imagen_texto` describe la foto para quien no puede verla; `imagen_pie` es un pie de foto opcional que sale bajo la imagen en la página del texto.
3. Mejor fotos verticales o cuadradas, de unos 1000 píxeles de ancho como mucho, para que la web cargue rápido.

Para corregir un texto ya publicado, ábrelo en `_posts`, pulsa el lápiz, cambia lo que sea y vuelve a pulsar *Commit changes*. Para borrarlo, los tres puntos (…) → *Delete file*. Empieza por borrar `2026-11-08-texto-de-ejemplo.md` (y su imagen, `assets/img/ejemplo.jpg`) cuando subas el primero de verdad.

### Cómo se escribe el texto (Markdown)

| Quieres… | Escribes… |
|---|---|
| *cursiva* | `*cursiva*` |
| **negrita** | `**negrita**` |
| un párrafo nuevo | una línea en blanco entre párrafos |
| una cita sangrada | `> ` al principio de la línea |
| un apartado | `## Título del apartado` |
| un separador entre partes | `***` solo en una línea |
| un enlace | `[texto que se ve](https://...)` |
| una nota al pie | `texto[^1]` y, al final, `[^1]: Contenido de la nota.` |
| una imagen | súbela a `assets/img/` y escribe `![descripción](/assets/img/foto.jpg)` |

Si escribes en Word o Google Docs, puedes pegar el texto y luego marcar las cursivas con asteriscos; las comillas «» y las rayas — se copian tal cual.

**Ojo:** el repositorio es público. Cualquier archivo que subas se puede ver en GitHub aunque no esté enlazado en la web, así que no subas borradores que no quieras enseñar.

---

## 3. Pasarlo a Substack

La web es el archivo principal; Substack es el envío por correo.

1. Cuando el texto ya esté en la web, ábrelo en el navegador, selecciona desde el título hasta el final y cópialo.
2. En Substack, crea una publicación nueva y pégalo: conserva cursivas, negritas, citas y enlaces.
3. Las notas al pie hay que rehacerlas con la herramienta de notas de Substack (el botón de nota del editor).
4. Si quieres, añade al final: *Publicado originalmente en [tu web](enlace)*.
5. Una vez publicado en Substack, copia su enlace y pégalo en el campo `substack:` del texto en `_posts`. Al final del texto en la web aparecerá una línea que remite a Substack.

---

## 4. Dominio propio (opcional, ~10–15 € al año)

1. Compra el dominio (por ejemplo `nuncasesabracomohayquecontaresto.com`; los dominios no admiten tildes) en un registrador: DonDominio, Namecheap, Cloudflare, etc.
2. En GitHub: *Settings* → *Pages* → *Custom domain*, escribe el dominio y guarda.
3. En el panel del registrador, en la configuración DNS del dominio, añade:
   - cuatro registros **A** para `@` con estas direcciones:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - un registro **CNAME** para `www` que apunte a `tu-usuario.github.io`
4. Espera (puede tardar desde minutos hasta un día), vuelve a *Settings* → *Pages* y marca *Enforce HTTPS*.
5. Cambia `url:` en `_config.yml` por la nueva dirección.

---

## Qué es cada cosa

- `_posts/` — tus textos. Es lo único que tocarás a menudo.
- `_config.yml` — título, lema, enlaces y nombres de las secciones.
- `sobre-mi.md` — la página «Sobre mí».
- `assets/css/estilo.css` — el diseño (colores, tipografía). Arriba del todo están los colores, por si quieres cambiarlos.
- `_layouts/` e `_includes/` — las plantillas. No hace falta tocarlas.
- La web genera sola un feed RSS en `/feed.xml`.

Si algo no aparece tras subir un cambio, mira la pestaña *Actions* del repositorio: si hay una cruz roja, al pulsarla se ve el error (normalmente, un fallo en la cabecera de un texto, como una comilla sin cerrar).
