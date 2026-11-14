# Mi Presupuesto

App para llevar el presupuesto mensual: ingresos, reparto en pago fijo, estilo de vida y ahorro, gastos del mes por tipo, tarjeta de crédito al mes siguiente, informe de consumo y metas de ahorro.

- **Android:** app instalable (APK), sin internet ni cuentas.
- **iPhone:** se instala desde Safari con "Agregar a inicio" y funciona sin internet.

Los datos se guardan solo en el teléfono. Para cambiar de celular o pasar datos entre Android e iPhone, usa el botón de copia de seguridad (la flecha hacia abajo, arriba a la derecha).

Este repositorio no contiene datos personales: la app empieza en cero, y tus datos se cargan con "Restaurar desde una copia".

## Subirlo a GitHub (una sola vez, desde una computadora)

1. Crea el repositorio: **+** → **New repository**.
   - Nombre: `mi-presupuesto`
   - Marca **Public**. GitHub Pages, que publica la versión de iPhone, solo es gratis en repositorios públicos.
   - No marques ninguna otra casilla. Toca **Create repository**.
2. Guarda la firma de la app: **Settings** → **Secrets and variables** → **Actions** → **New repository secret**.
   - Name: `KEYSTORE_BASE64`
   - Secret: pega todo el texto del archivo `CLAVE_FIRMA_KEYSTORE_BASE64.txt`.
   - Toca **Add secret**.
3. Activa la página web: **Settings** → **Pages** → en **Source** elige **GitHub Actions**.
4. Vuelve a la pestaña **Code**, toca **uploading an existing file** y arrastra **todo el contenido** de la carpeta `MiPresupuesto` (incluida la carpeta `.github`). Toca **Commit changes**.
   - No subas `CLAVE_FIRMA_KEYSTORE_BASE64.txt` ni `mi-presupuesto-noviembre.json`.
5. Comprueba que aparece la carpeta `.github`. Si no aparece:
   - Toca **Add file** → **Create new file**.
   - Escribe exactamente `.github/workflows/build.yml` como nombre.
   - Pega el contenido de ese archivo y toca **Commit changes**.
6. En la pestaña **Actions**, espera a que "Publicar app" termine con check verde (unos 5 minutos).
   - Si sale en rojo, entra, toca **Re-run all jobs** y, si vuelve a fallar, copia el mensaje de error.

## Instalar en Android

1. En el celular, abre `github.com/TU-USUARIO/mi-presupuesto`.
2. Toca **Releases** → la versión más reciente → **MiPresupuesto.apk**.
3. Abre el archivo. Si Android lo pide, permite **instalar apps desconocidas** para tu navegador o la app de Archivos.
4. Si aparece Play Protect, toca **Más detalles** → **Instalar de todas formas**. Sale porque la app no viene de la Play Store.
5. Abre la app → botón de copia (arriba a la derecha) → **Restaurar desde una copia** → elige `mi-presupuesto-noviembre.json`.
   - Antes tienes que tener ese archivo en el celular: mándatelo por WhatsApp o súbelo a Drive.

## Instalar en iPhone (cuando lo necesites)

1. Abre **Safari** (tiene que ser Safari) y entra a `https://TU-USUARIO.github.io/mi-presupuesto/`.
2. Toca **Compartir** (el cuadrado con la flecha) → **Agregar a inicio** → **Agregar**.
3. Abre la app desde el ícono nuevo.
4. Para pasar tus datos, en Android haz **Guardar copia** y luego, en el iPhone, **Restaurar desde una copia**.

En iPhone, **Guardar copia** abre el menú Compartir: elige "Guardar en Archivos", Drive o WhatsApp.

## Actualizaciones

Cada cambio que se sube al repositorio publica una versión nueva:

- **Android:** descarga el APK nuevo de Releases e instálalo encima del anterior. Tus datos se mantienen porque todas las versiones usan la misma firma, la del secreto `KEYSTORE_BASE64`. Guarda `CLAVE_FIRMA_KEYSTORE_BASE64.txt` en un lugar seguro: sin él, una actualización obligaría a desinstalar.
- **iPhone:** la app se actualiza sola la próxima vez que la abras con internet.

Si desinstalas la app o borras el ícono del iPhone, sus datos se borran. Guarda antes una copia de seguridad.
