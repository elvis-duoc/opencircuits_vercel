# OpenCircuits Web · versión para Vercel

Esta carpeta es OpenCircuits **ya construido**, listo para publicarse gratis como sitio estático (GitHub + Vercel).
No se edita a mano: se genera desde la carpeta `opencircuits` con `npm run web`.

## Qué funciona en la web

| Funciona | No funciona en la web |
|---|---|
| Armar circuitos, todas las piezas y la simulación | Compilar un programa **nuevo o modificado** |
| Programar con bloques y texto, ver el código | (para eso: `Iniciar.bat` en el computador del taller) |
| Todos los ejemplos y el menú **Secuencias por equipo**, simulando su programa tal como viene, con sus **Retos** | |
| Revisar, Calibrar, Explicar, Monitor en serie, Depurador | |
| Guardar / abrir proyectos `.circuit`, exportar PNG, PDF, INO | |
| **Arduino real por USB** (Chrome o Edge) con los programas de los ejemplos | |

Vercel no tiene el compilador de Arduino, así que los programas de los ejemplos se compilan de antemano y van en
`assets/firmware/`. Si un estudiante cambia el código o un umbral, la web le avisa que use `Iniciar.bat` para compilar.
Cada estudiante guarda su trabajo en su propio navegador.

## Publicar por primera vez

### 1. Subir la carpeta a GitHub
La carpeta tiene muchos archivos (la página web de GitHub solo acepta 100 a la vez), así que conviene **GitHub Desktop**:

1. Instale GitHub Desktop (<https://desktop.github.com>) e inicie sesión.
2. **File → Add local repository…** → elija esta carpeta `opencircuits_vercel` → *create a repository* → **Create repository**.
3. **Publish repository** (puede dejarlo privado). Listo: queda en su cuenta de GitHub.

Con la terminal es lo mismo:
```
git init
git add .
git commit -m "OpenCircuits web"
git branch -M main
git remote add origin https://github.com/SU_USUARIO/opencircuits-web.git
git push -u origin main
```

### 2. Vincular con Vercel
1. Entre a <https://vercel.com> con su cuenta de GitHub (plan **Hobby**, gratis).
2. **Add New… → Project** → elija el repositorio → **Import**.
3. *Framework Preset*: **Other**. No cambie nada más (el archivo `vercel.json` ya indica que no hay que construir nada).
4. **Deploy**. Vercel le entrega una dirección como `https://opencircuits-web.vercel.app`.

## Actualizar la web después de cambios

1. En la carpeta `opencircuits`: `npm run web` (regenera los ejemplos, construye la app, compila los programas de los
   ejemplos y reescribe esta carpeta; conserva la carpeta `.git`).
2. En GitHub Desktop: **Commit to main** → **Push origin**. Vercel publica la nueva versión solo, en un minuto.
