# Grillo de bolsillo

Versión para móvil de GRILLO: mismo motor de sonido y mismos proyectos `.grillo` que la versión de ordenador.

- **Android:** APK que se genera solo en GitHub (pestaña *Releases*).
- **iPhone (y cualquier móvil):** la misma app como página web, que se instala con «Añadir a pantalla de inicio».

## Puesta en marcha (una sola vez)

1. **Crea un repositorio nuevo en GitHub**, por ejemplo `grillo-bolsillo`, de tipo **público**. La página web gratuita de GitHub solo funciona con repositorios públicos.
2. **Sube el contenido de esta carpeta**, no la carpeta en sí: `www`, `android-res`, `.github`, `package.json`, `capacitor.config.json`, `README.md` y `.gitignore`.
   - Si lo subes desde la web de GitHub («Add file → Upload files»), la carpeta `.github` a veces no se ve al arrastrar. Comprueba que existe `.github/workflows` con los dos archivos `.yml`.
3. **Guarda la clave de firma** (para que las actualizaciones del APK se instalen encima sin perder tus proyectos):
   - *Settings → Secrets and variables → Actions → New repository secret*
   - Nombre: `KEYSTORE_B64`
   - Valor: todo el texto del archivo `NO-SUBIR-clave-KEYSTORE_B64.txt`. Ese archivo **no** se sube al repositorio. Guárdalo en un sitio seguro.
4. **Activa la página web:** *Settings → Pages → Build and deployment → Source: GitHub Actions*.
5. Ve a la pestaña **Actions** y lanza los dos trabajos («APK Android» y «Web (iPhone)») con *Run workflow*. Después se lanzan solos cada vez que subas cambios.

## Instalar

**Android**
- Abre en el móvil la página del repositorio → *Releases* → la última versión → descarga `Grillo.apk`.
- Ábrelo e instálalo. La primera vez Android te pedirá permiso para instalar apps de esa fuente.
- Para actualizar, instala el APK nuevo encima: los proyectos y las muestras se conservan.

**iPhone**
- Abre en Safari `https://TU-USUARIO.github.io/grillo-bolsillo/` (el enlace sale en *Settings → Pages*).
- Botón Compartir → **Añadir a pantalla de inicio**. Se abre con su icono, a pantalla completa, y funciona sin conexión.

## Actualizar la app

Sustituye la carpeta `www` por la nueva y súbela. Los dos trabajos se lanzan solos: sale un APK nuevo en *Releases* y la web se actualiza.
