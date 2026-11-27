# Cambios

Las notas de cada release se toman de aquí: la sección `## <versión>` del tag que se publica.

## 0.4.2

- Vídeo (macOS): se reproducen **WebM** con VP9 o AV1 y audio Opus, y MP4 con VP9 o AV1. El
  WebM no se recodifica: se reenvuelve como MP4 en la caché la primera vez. AV1 necesita un Mac
  que lo decodifique (M3 o posterior); VP8 y el audio Vorbis no se admiten.
- Corregido: si el archivo de un vídeo cambiaba en disco con Kern abierto, se seguía usando el
  anterior hasta reiniciar; ahora se vuelve a abrir al compilar o con *Archivo → Recargar*.
- **Acerca de Kern** (menú *Kern* en macOS y *Ayuda*): muestra la versión.

## 0.4.1

- Menú **Ayuda → Notas, GIF y vídeo en el documento…**: muestra la sintaxis y copia el ejemplo
  de vídeo al portapapeles.
- Vídeo: barra de progreso translúcida en su borde inferior (vista y presentador); un clic o un
  arrastre sobre ella lo lleva a ese punto.
- ↑ y ↓ pasan de diapositiva (con la lupa puesta siguen cambiando su aumento), y también la rueda
  del ratón o el trackpad sobre la diapositiva ajustada a la ventana.
- Al saltar de la vista al código, el editor centra la línea de destino y la resalta hasta que
  muevas el cursor; el cursor del editor es ahora azul.
- Corregido (macOS): una ventana de Kern tapada del todo por otra (p. ej. la de presentación,
  compartida en una videollamada, detrás de la principal mientras editas) no se redibujaba
  hasta traerla al frente; ahora pinta cada cambio aunque esté tapada, y los vídeos y GIF siguen
  corriendo en ella (a unos 20 cuadros por segundo).
- Corregido: la vista podía quedarse con la imagen anterior de una página si esta cambiaba de
  posición (al añadir o quitar otra antes) mientras se dibujaba.

## 0.4.0

### Vista
- **GIF animados**: un `#image("demo.gif")` se ve animado en la vista, el presentador y la
  ventana de presentación (en el PDF y las exportaciones sigue fijo en su primer cuadro).
- **Vídeo** (solo macOS por ahora): `#metadata((t: "Video", v: "demo.mp4")) <kern>` antes de la
  imagen de póster; se reproduce con audio encima del póster al entrar en la diapositiva. Tecla
  `v` para pausar o reanudar; opciones `loop` y `mute`.

## 0.3.0

### Editor
- Cambios hechos en disco por otro programa (p. ej. una IA) mientras editas: si no chocan con lo
  tuyo se integran solos; si chocan, una barra deja elegir «Usar la del disco», «Conservar la
  mía» o «Resolver a mano» (marcas `<<<<<<<` / `>>>>>>>`). Al recargar se conservan cursor y ⌘Z.
- **Recargar** (Archivo → Recargar, ⌘R / Ctrl+R): relee las pestañas del disco y compila desde
  cero; el aviso dice la hora de la compilación.

## 0.2.0

Primera versión con el nombre **Kern** (antes, Typst Viewer).

### Editor
- Pestañas: abre otros archivos del proyecto (⌘⇧O / Ctrl+Shift+O); un clic en la vista sobre algo
  de otro archivo abre su pestaña.
- Buscar y reemplazar (menú **Editar**, ⌘F y ⌘⇧F / Ctrl+F y Ctrl+H).
- **Modo Vim** (Editar → Modo Vim): modos, movimientos con cuenta, `d` `c` `y` con movimientos y
  objetos de texto, `p`, `u`, `.`, `/`, `:w`, `:q`.
- Navegación código ↔ vista: un clic en la diapositiva (también en zonas vacías o en una
  miniatura) lleva al código que la produjo, y mover el cursor lleva la vista a su página. Con el
  editor cerrado, ⌘-clic / Ctrl-clic lo abre y salta.
- Resaltado incremental: escribir en archivos grandes ya no se nota (1,4 ms por tecla con 5000
  líneas).

### Colaboración
- Se comparte todo el proyecto (archivos importados, imágenes, bibliografía), no solo el archivo
  principal.
- Cursores y nombres de los demás en el editor; modo **Seguir al anfitrión**.
- El apuntador láser y la pantalla en negro del anfitrión se ven en los demás equipos.
- Permisos: admitir a mano a quien entra, máximo de invitados, solo lectura por persona y sacar
  de la sesión.
- Chat de la sesión (⌘⇧M / Ctrl+Shift+M).
- ⌘Z en una sesión deshace solo lo propio; reconexión automática, copiar el ticket otra vez y
  conexión por relay sin DNS.

### Otros
- El ticket ahora empieza por `kern:`; no se puede compartir sesión con versiones anteriores.
- Las variables de entorno pasan a ser `KERN_NAME` y `KERN_NET`.
- La configuración (recientes y preferencias) se mueve sola a la carpeta `kern`.
