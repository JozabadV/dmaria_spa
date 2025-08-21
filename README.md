# D'Maria Spa - Prototipo APK (Flutter)

Este es un prototipo funcional con:
- Registro y edición de **Clientes**
- Registro de **Servicios** por cliente
- **Exportación** de clientes por tipo de servicio a **CSV/TXT** y compartir (WhatsApp, correo, etc.)
- Pantalla de bienvenida con el **logo de D'Maria Spa**

## Cómo compilar el APK (opción nube - Codemagic)

1) Crea una cuenta en https://codemagic.io (gratuita) e inicia sesión.
2) Crea un nuevo **App** conectando tu repositorio (o usa **App -> Build without repository** y sube este ZIP).
3) Asegúrate de seleccionar plataforma **Flutter**.
4) Codemagic leerá el archivo `codemagic.yaml` y ejecutará:
   - `flutter create .` si faltan carpetas de plataforma (android/ios)
   - `flutter pub get`
   - `flutter build apk --release`
5) Cuando termine, descarga el archivo de artefacto: `app-release.apk`.
6) Instálalo en tu Android (habilita "Instalar apps de orígenes desconocidos" si lo pide).

## Cómo compilar localmente (opción PC con Android Studio)

1) Instala **Flutter SDK** y **Android Studio**.
2) Abre este proyecto en Android Studio.
3) Ejecuta en terminal:
   ```bash
   flutter pub get
   flutter build apk --release
   ```
4) El APK estará en `build/app/outputs/flutter-apk/app-release.apk`.

## Notas de uso
- En **Clientes** puedes agregar/editar/eliminar.
- En **Servicios** selecciona un cliente, agrega servicios (tipo, fecha y notas).
- En **Exportar** elige un **tipo de servicio** y genera **CSV** o **TXT**. Se generará el archivo y podrás **compartirlo** (WhatsApp Business recomendado).
- La base de datos es local (SQLite). Este prototipo no requiere Internet.

## Próximos pasos sugeridos
- Validación de teléfono (solo dígitos y formato internacional).
- Recordatorios de citas vía WhatsApp (manual desde listas de difusión) o integración con API oficial.
- Sincronización en la nube (ej. Firebase) y panel web.
