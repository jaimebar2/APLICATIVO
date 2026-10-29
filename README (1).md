# Evaluador de inversión industrial

Herramienta web para evaluar si una inversión en una empresa industrial es viable. Hace preguntas, pide documentos según el tipo de sociedad, el tamaño y el sector, calcula una calificación de 0 a 100 y, si la calificación es baja, propone un plan de mejora.

## Qué contiene

| Archivo | Para qué sirve |
| --- | --- |
| `index.html` | La aplicación completa (HTML, CSS y JavaScript en un solo archivo) |
| `server.js` | Servidor mínimo en Node que entrega `index.html` y lee el puerto de Railway |
| `package.json` | Le indica a Railway cómo arrancar (`npm start`) |
| `.gitignore` | Archivos que Git no debe subir |

No tiene dependencias, así que no hace falta `npm install`.

## Probar en tu computador

Necesitas Node 18 o superior.

```bash
npm start
```

Abre http://localhost:3000

## Subir a GitHub

1. Crea un repositorio nuevo en GitHub (por ejemplo `evaluador-inversion`).
2. Sube los cuatro archivos a la raíz del repositorio. Desde la web: botón **Add file → Upload files**, arrastra los archivos y confirma con **Commit changes**.

Con Git en la terminal:

```bash
git init
git add .
git commit -m "Primera versión"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/evaluador-inversion.git
git push -u origin main
```

## Desplegar en Railway

1. Entra a https://railway.com e inicia sesión con tu cuenta de GitHub.
2. **New Project → Deploy from GitHub repo** y elige el repositorio.
3. Railway detecta Node, usa `npm start` y asigna el puerto solo.
4. Cuando termine el despliegue, abre **Settings → Networking → Generate Domain** para obtener la dirección pública.

Cada vez que hagas un cambio en la rama `main`, Railway vuelve a desplegar.

## Notas

- Los datos que se escriben en la herramienta se guardan solo en el navegador de cada persona (localStorage). No hay base de datos ni cuentas de usuario.
- Las tipografías vienen de Google Fonts, por lo que la página necesita conexión a internet para verse como está diseñada.
- Las referencias por sector (liquidez, endeudamiento, rentabilidad) están en el objeto `SECTORS` dentro de `index.html`. Son orientativas: ajústalas con datos reales de tu sector.
- Las preguntas están en la lista `Q` y los pesos de cada área en `AREA_W`, también dentro de `index.html`.
- La herramienta ayuda a filtrar inversiones y no reemplaza el análisis de un asesor financiero ni la revisión de un abogado.
