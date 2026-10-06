# MiniYo · guía rápida

App web (PWA) con tu avatar, la ciudad y el tiempo, y toda tu vida organizada en siete pestañas. Funciona sin servidor: todo se guarda en el propio dispositivo.

## Cómo colgarlo en GitHub Pages
Sube el CONTENIDO de esta carpeta a la raíz de `main` (no una carpeta MiniYo dentro del repo).

Obligatorio:
- `index.html`, `sw.js`, `manifest.webmanifest`, `.nojekyll`
- `icon-192.png`, `icon-512.png`, `apple-180.png`
- la carpeta `img/` con todas las imágenes
- las mismas imágenes también en la raíz (sirven de respaldo)

Después de subir espera 1-2 minutos y recarga dos veces en el móvil (la caché de la versión anterior tarda en soltarse). Versión actual de la caché: `miniyo-piloto-v22` en `sw.js`; súbela de número cuando cambies archivos.

URL: https://alalvarez-arch.github.io/MiniYo/

## Pestañas
| Pestaña | Qué hay |
|---|---|
| **Inicio** (centro) | Avatar, tiempo, frases, resumen de pendientes, importante y compra. Botones: ✎ editar avatar, 🧰 baúl (copia de seguridad y guía), 💬 panel de guardado, + añadir |
| **Hogar** | Tipo de casa (piso, casa, chalet, adosado, ático, casa de pueblo, loft), régimen, cuota de hipoteca o alquiler, papeles y fechas |
| **Vehículo** | Varios vehículos (coche, moto, patinete, abono), color de carrocería, ITV, seguro, impuesto, cuota, papeles |
| **Salud** | Cuestionario inicial, medicamentos, enfermedades comunes, citas (médico, dentista, fisio…) |
| **Mascota** | Perros y gatos enteros, collar antimosquitos, pastillas de parásitos internos y externos con fechas, citas del veterinario |
| **Trabajo** | Sector con su escena, uniforme para el avatar, profesión, horario semanal continuo o partido, duplicar por semana o mes, aviso trimestral de IVA/IRPF si eres autónomo |
| **Hobby** | Deportes y aficiones editables (✎). Cada una trae sus propias opciones: pádel (reservar pista, pelotas, partidos), pintura (lienzos, pinturas, pinceles), gimnasio (suscripción, clases)… con días y hora, detalles, cuota, lista de deseos y fechas |

Cada pestaña muestra sus propios **avisos y citas**, y el punto de color de la barra indica urgencia (rojo ≤ 7 días, amarillo ≤ 30, verde más lejos).

## Compra y pendiente
- **Pendiente**: categorías desplegables (Hogar, Vehículo, Salud, Mascota, Trabajo, Hobby, Otros).
- **Compra**: categorías y secciones tuyas (Nevera → Congelados, Verduras…; Hogar → Cocina, Dormitorio…). Se pueden crear categorías y secciones nuevas.
- Botón **+**: eliges Dónde, Para, Sección y fecha. Se clasifica solo si lo dejas en Auto.
- Panel **💬**: escribe frases como «yogures en nevera», «cita dentista el viernes a las 17:30» o «borra leche».

## Baúl (copia de seguridad)
El botón 🧰 guarda todo en un archivo `.json` y lo carga en otro móvil u ordenador. Hazlo de vez en cuando: los datos viven solo en el dispositivo.

## Guía interactiva
La primera vez que abres la app, una guía te lleva por Inicio y por cada pestaña explicando qué hay. Se puede saltar, y se repite desde el baúl (🧰 → "Ver la guía otra vez"). Para que vuelva a salir a todos, quita `tourDone` del estado o sube la versión del guardado.

## Carácter y personalidad
- **Carácter** (tierno, serio, malote): cómo habla y se comporta tu miniyo.
- **Personalidad** (normal, rockero, deportista, tatuado, estudiante): su estilo y su ropa. Se cambian en el alta y en ✎.

## Cómo añadir imágenes
Todas son WebP/JPG en `img/` (y copia en la raíz).

- **Avatares de estilo**: `img/av-<estilo>-<h|m>-<joven|media|mayor>.webp`, con estilos `rockero`, `deportista`, `tatuado`, `estudiante` (24 imágenes, ya incluidas). Aparecen junto a Tierno, Serio y Malote en el alta inicial y en el botón ✎. Recorta el fondo para que no se vea el estudio.
- **Uniformes**: `img/un-<oficina|salud|taller|barra>-<h|m>.webp`. Se usan según el sector (oficina→oficina; salud y veterinaria→salud; obra, taller y campo→taller; hostelería, cocina y panadería→barra). Se activan en Trabajo ("Ponerme el uniforme") o en ✎ → "Uniforme de trabajo". Para añadir otro, copia la imagen y añade el sector en `UNIF` dentro de `index.html`.
- **Casas**: `img/casa-<tipo>.webp` y la línea `HOUSE` en `index.html`.
- **Trabajos**: `img/trabajo-<sector>.webp` y la línea del sector en `JOB`.
- Prompt base para generar figuras con el mismo estilo: figura 3D de plastilina, cuerpo entero, de frente, fondo liso beige, misma luz suave.

## Contenido de la carpeta img/
- `av-*`: avatares de estilo (rockero, deportista, tatuado, estudiante) por género y edad. `un-*`: uniformes de trabajo.
- `h-*`, `m-*` y similares: avatares originales (hombre, mujer) recortados.
- `casa-*`: tipos de vivienda. `trabajo-*`: escenas por sector.
- Coches (`dSFN8`, `2I6fx`, `KjjS4`, `7HJH6`, `6RP61`, `vEa74`) y mascotas (`perro`, `gato`, `beagle`…).
- `cloud-*.webp`: nubes del cielo.

## Qué falta
- Uniformes para educación, comercio, transporte y otros sectores (hasta entonces el avatar sigue con su estilo).
- Algunos recortes siguen con restos pequeños de suelo o zapatillas blancas algo irregulares (deportistas, tierno mayor, estudiante joven mujer). Con imágenes sobre fondo de color distinto a la ropa saldrían limpios.
