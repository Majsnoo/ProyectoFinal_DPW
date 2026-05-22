# ProyectoFinal_DPW

Este repositorio contiene una página estática (HTML + CSS) lista para desplegar en GitHub Pages.

Instrucciones rápidas para publicar en GitHub Pages:

1. Crea un repositorio en GitHub (por ejemplo `ProyectoFinal_DPW`).
2. Desde la carpeta del proyecto en tu máquina, ejecuta:

```powershell
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/USUARIO/REPO.git
git push -u origin main
```

Sustituye `USUARIO` y `REPO` por tu usuario y el nombre del repositorio.

3. En GitHub, ve a `Settings` → `Pages` y configura el despliegue desde la rama `main` y la carpeta `/ (root)`.

4. Después de unos segundos, GitHub te dará una URL pública: `https://USUARIO.github.io/REPO/`.

Consejo: si prefieres, puedes usar la CLI `gh` para crear el repo y desplegar:

```powershell
gh repo create USUARIO/REPO --public --source=. --push
```

Problemas comunes:
- Si usas rutas relativas a la raíz, la URL funcionará correctamente.
- Para prevenir que GitHub procese con Jekyll, he añadido un archivo `.nojekyll`.

Archivos añadidos:
- `.nojekyll` — evita el procesamiento Jekyll en GitHub Pages.

Si quieres, puedo crear el repositorio por ti (necesitaré un token) o configurar una GitHub Action para desplegar automáticamente.
