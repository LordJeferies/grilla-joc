# Grilla JOC

<!-- GRILLA_JOC_PROJECT_V1 -->

Calendario e inventario editorial: 21 publicaciones principales y 6 extras opcionales. TBT el jueves y tip personal el miércoles.

Versión 7: dashboard de trabajo con métricas reales de inventario, 16 fijos L1 + 5 piezas de serie L2 dentro de las 21 principales, 6 extras, faltantes por semana, correcciones abiertas y navegación móvil inferior. Conserva las ventanas compatibles y el retorno a la ficha.

## Qué contiene

- Calendario combinado 21+6; seis extras en violeta.
- Semanas desplegables dentro de Piezas y Drive; opción de ver sólo las 21 principales.
- Listas de piezas concretas con nombre, carpeta o archivo de Drive, fecha tentativa, estado y notas.
- Mini chat por pieza: notas y correcciones, pendiente/en proceso/resuelta, indicadores en el calendario.
- Un enlace nuevo comienza sin confirmar. Resolver una corrección no confirma automáticamente la pieza terminada.
- Cobertura por grupo y semanas completas; cada recurso se consume una sola vez en la previsión.
- Navegación, asistentes y comparación de escenarios. Sin librerías externas ni servidor de datos.

## Publicar desde Mac

Extrae el ZIP completo y ejecuta:

```bash
bash "$HOME/Downloads/grilla-joc/PUBLICAR_GRILLA_JOC.command"
```

El script usa la cuenta activa de GitHub CLI, crea o actualiza su repositorio **público** `grilla-joc`, configura GitHub Pages mediante Actions y espera el resultado. La carpeta de trabajo queda en `~/Downloads/grilla-joc-publicacion`. No usa force-push, no cambia un repositorio privado a público y no sustituye repositorios ajenos al identificador de este proyecto.

Si falta GitHub CLI y tienes Homebrew, lo instala. Si falta sesión, abre el login oficial. Si un token existente carece del permiso para subir workflows:

```bash
gh auth refresh --hostname github.com --scopes repo,workflow
```

Para actualizar, sustituye `index.html` en el paquete y vuelve a ejecutar el script. La carpeta de publicación debe estar limpia.

## Datos e inventario

La página y el código son públicos. El inventario que introduces y los enlaces Drive se guardan en el navegador; el paquete y el workflow no incluyen las copias JSON que exportes. Exportar/Importar permite mover registros a otro dispositivo. No hay sincronización automática entre navegadores, verificación automática de Drive ni publicación en redes sociales.

Las notas normales no bloquean disponibilidad. Una corrección pendiente o en curso sí bloquea; al resolverla se requiere confirmación final. Reservar es una acción interna, no una programación real en redes.

Los calendarios y ejemplos visuales describen el sistema editorial. No se consideran contenido confirmado ni publicado.

## Referencias de publicación

- https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages
- https://docs.github.com/en/rest/pages/pages
- https://cli.github.com/manual/gh_repo_create

## Validación

Sintaxis del HTML/JavaScript, lógica de conteo y pruebas DOM de calendario, inventario y chat verificadas localmente. También se verificaron todos los enlaces de menú y las ventanas anidadas sin APIs nativas de dialog, en entornos DOM de 390 y 1440 px. La revisión visual en Safari/iPhone y el despliegue real requieren ejecutar y abrir la página. El paquete no se ha publicado automáticamente desde el chat.

Si abres el HTML descargado en iPhone, usa Safari. Algunas vistas previas de archivos no ejecutan JavaScript; en ellas los controles no pueden funcionar.
