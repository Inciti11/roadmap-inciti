# Roadmap Inciti

Página del roadmap del Investor Portal, lista para GitHub Pages.
La "base de datos" es el archivo `data.json` de este mismo repositorio:
cada cambio que se hace en la página se guarda ahí como un commit.

## Archivos

- `index.html`: la página completa (diseño, logo y lógica).
- `data.json`: los datos (etapas, tareas, fechas y avance). Ya trae lo que el equipo había marcado.

## 1. Subir a GitHub

1. Crea un repositorio nuevo, por ejemplo `roadmap-inciti`.
2. Sube `index.html`, `data.json` y este `README.md` a la rama `main`.
3. Ve a **Settings → Pages**.
4. En **Source** elige **Deploy from a branch**, rama `main`, carpeta `/ (root)` y guarda.
5. En uno o dos minutos la página queda en `https://USUARIO.github.io/roadmap-inciti/`.

No hay que configurar nada más: la página detecta sola el usuario y el repositorio.
Si la publicas en un dominio propio, llena `owner` y `repo` en el bloque `const GH` de `index.html`.

## 2. Crear el token para poder editar

Cualquiera con el enlace puede **ver** el roadmap. Para **editar** (marcar tareas, cambiar fechas, usar Editar) cada persona necesita un token:

1. En GitHub: foto de perfil → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. **Repository access**: *Only select repositories* → elige `roadmap-inciti`.
3. **Permissions → Repository permissions → Contents**: *Read and write*.
4. Pon una fecha de vencimiento y crea el token. Cópialo.
5. Abre la página → **Avance general** → **Conectar para editar** → pega el token → **Conectar**.

El token queda guardado solo en ese navegador. Con **Desconectar** se borra.

## Cómo funciona

- Los cambios se guardan en `data.json` unos segundos después de hacerlos.
- Si dos personas guardan casi al mismo tiempo, la página mezcla las tareas y fechas de ambas y vuelve a guardar.
- Quien edita ve los datos al instante. Quien solo mira ve los cambios cuando GitHub Pages se actualiza (normalmente en 1 o 2 minutos).
- La página revisa si hay cambios nuevos cada 45 segundos.
- Todo cambio queda en el historial de commits, así que cualquier versión anterior se puede recuperar.

## Importante

- **Privacidad**: en un repositorio público, `data.json` lo puede leer cualquiera. GitHub Pages con repositorio privado requiere un plan pago (Pro, Team o Enterprise).
- **Nunca** pegues el token dentro de `index.html` ni lo subas al repositorio: con él se puede escribir en el repo.
- Si el repositorio es de una organización, puede que un administrador tenga que aprobar los tokens.
