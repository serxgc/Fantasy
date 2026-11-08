# Cartera Fantasy

App web para llevar tu plantilla de LaLiga Fantasy: jugadores fichados, ventas, beneficio realizado y una calculadora de deuda. Funciona en el navegador, se puede instalar en la pantalla de inicio del móvil y también sin conexión. No necesita servidor ni cuenta.

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La app completa |
| `manifest.webmanifest` | Datos para instalarla como app |
| `sw.js` | Permite usarla sin conexión |
| `icon-192.png`, `icon-512.png` | Iconos de la app |

Estos cinco archivos van en la raíz del repositorio.

## Publicarla con GitHub Pages

1. Crea un repositorio nuevo, por ejemplo `cartera-fantasy`, y márcalo como **público**.
2. Pulsa **Add file → Upload files**, sube los cinco archivos y confirma con **Commit changes**.
3. Ve a **Settings → Pages**. En *Source* elige **Deploy from a branch**, rama `main` y carpeta `/ (root)`. Guarda.
4. Espera uno o dos minutos. La app estará en `https://TU-USUARIO.github.io/cartera-fantasy/`.

## Instalarla en el móvil

Abre la dirección en Chrome, pulsa ⋮ y elige **Instalar app** o **Añadir a pantalla de inicio**. Con esa dirección el acceso directo no caduca.

## Primer uso

La app arranca vacía, porque los datos nunca se suben al repositorio. Si tienes una copia `.json`, entra en **Más → Restaurar copia** y elígela. Si no, empieza con **Fichar**.

**No subas tu copia `.json` a GitHub.** El repositorio es público y cualquiera podría verla.

## Cómo se usa

- **Plantilla:** tus jugadores agrupados por posición, con el precio al que los compraste. Toca uno para venderlo o editarlo.
- **Vendidos:** cada venta con su beneficio. Puedes ordenarlas por recientes, mejores o peores.
- **Fichar y Vender:** los botones de abajo. El importe se escribe en € o en millones (`5.500.000`, `5,5`) y la app te enseña cómo lo ha entendido antes de guardar.
- **Deshacer:** el aviso tras cada operación, o **Más → Deshacer última operación**.
- **Totales:** arriba ves lo invertido en la plantilla y el beneficio realizado.

## Calculadora de deuda (pestaña Deuda)

Escribe tu valor de equipo, tu saldo (con signo − si estás en deuda) y el límite de deuda, que por defecto es el 20 %. Opcionalmente añade ventas previstas (oferta y valor del jugador) y los fichajes que quieres hacer (precio y valor).

La regla que usa:

- **Deuda máxima** = límite × valor de equipo.
- **Poder de compra** = saldo + deuda máxima.
- Las pujas no suman al valor de equipo hasta cerrarse, así que para pujar se usa el valor de equipo de ahora.
- Cada 1M que vendes a su valor te da solo 0,8M de margen, porque también baja tu límite de deuda.

Tiene dos modos: **Pujas a la vez** (todos los fichajes con el valor de equipo actual) y **Uno tras otro** (cada fichaje cerrado suma su valor antes del siguiente, con una tabla paso a paso). Te dice si puedes fichar, cuánto te falta, cuánto tendrías que vender y la deuda que te queda después. Lo que escribes se guarda solo.

Es un cálculo basado en lo que se ha observado en una liga concreta. Si el juego aplica otra regla, los números pueden no coincidir.

## Copias de seguridad

Los datos se guardan en el navegador del dispositivo, no en la nube. Si borras los datos del navegador, cambias de teléfono o desinstalas la app, se pierden.

- **Más → Guardar copia (.json):** descarga un archivo con todo.
- **Más → Restaurar copia:** carga un archivo guardado antes.
- **Más → Resumen para pegar:** texto con tu plantilla y los totales.

Guarda una copia cada pocos días.

## Actualizar la app

Sustituye `index.html` (y `sw.js` si ha cambiado) en el repositorio con **Add file → Upload files**. Tus datos no se tocan, porque viven en el navegador. Si el móvil sigue mostrando la versión anterior, ciérrala del todo y ábrela de nuevo con conexión.

## Límites

- No lee capturas de pantalla: los fichajes y las ventas se apuntan a mano.
- No incluye todavía el gasto en cláusulas.
- Si el navegador no permite guardar datos, aparece arriba "Este navegador no guarda datos". En ese caso usa Chrome y guarda copias antes de cerrar.
