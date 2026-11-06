# Cambios

Las notas de cada release se toman de aquí: la sección `## <versión>` del tag que se publica.

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
