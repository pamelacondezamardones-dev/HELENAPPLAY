# HelenAPP Mi Voz — Paquete para Google Play (octubre de 2026)

## Qué incluye
- Proyecto Android Studio (carpeta `app`, `settings.gradle`, `build.gradle`).
- HTML original con aceptación de términos y todas las frases en `app/src/main/assets/`.
- Motor de voz nativo Android para que los botones de hablar funcionen en WebView.
- Ícono de 512 × 512 y gráfico destacado de 1024 × 500.
- Ficha de tienda y borrador de política de privacidad.
- Copia web para GitHub Pages.

## Qué falta antes de subir a Play Console
**Este ZIP NO contiene un archivo AAB firmado.** Se debe generar con Android Studio y una clave de firma privada propia. Tampoco incluye capturas reales, que deben tomarse tras probar la app en un teléfono.

1. Instala Android Studio desde https://developer.android.com/studio.
2. Abre la carpeta `HelenAPP_Google_Play_2026` como proyecto.
3. Instala Android SDK 36 cuando Android Studio lo solicite. El proyecto apunta a Android 16 (API 36), requisito para apps nuevas en octubre de 2026.
4. Ejecuta la app en un teléfono Android y prueba especialmente voz, favoritos, primera aceptación, reinicio, modo avión y accesibilidad.
5. Antes de distribuir, revisa el identificador `cl.helenapp.mivoz`; una vez publicada, cambiarlo crea otra app.
6. Selecciona Build > Generate Signed Bundle / APK > Android App Bundle. Crea y **respalda fuera del proyecto** tu clave de firma; nunca la publiques en GitHub ni la compartas.
7. Registra una cuenta en https://play.google.com/console, crea la aplicación gratuita y completa los datos requeridos.
8. Publica `documentos_legales/politica_privacidad.html` como página web accesible sin inicio de sesión (por ejemplo en GitHub Pages) y copia su URL a Play Console.
9. Completa Data safety según la implementación Android real, incluyendo las prácticas del motor TTS usado en los dispositivos de prueba. No marques respuestas sin verificarlas.
10. Agrega ícono, gráfico destacado y capturas reales, así como las descripciones de `material_tienda/ficha_google_play.txt`.
11. Completa clasificación de contenido, público objetivo y pruebas requeridas para tu tipo de cuenta. Sube el AAB firmado a la pista de prueba, revisa los informes y solicita publicación.

## Observaciones técnicas
- Se empaqueta el HTML dentro de la app; no depende de GitHub Pages para abrirse.
- La voz se comunica con TextToSpeech nativo mediante una interfaz JavaScript limitada al HTML local. No se cargan URLs externas en el WebView.
- La primera aceptación se guarda en el almacenamiento local de WebView; no debe reaparecer mientras se conserven los datos.
- Las voces instaladas pueden variar según el dispositivo. La disponibilidad de español de Chile debe comprobarse.
- La política incluida es un borrador que describe esta implementación; verificarla antes de publicar.
- La ausencia de `gradlew` significa que Android Studio deberá configurar Gradle en el equipo; no se ha compilado ni probado un AAB en este entorno.
- Si en el futuro agregas conexión a Internet, SDK de terceros o analítica, debes revisar permisos y política de privacidad.

## Fuentes oficiales
- API requerida: https://support.google.com/googleplay/android-developer/answer/11926878
- Política de privacidad y Data safety: https://support.google.com/googleplay/android-developer/answer/18258653
- Android Studio: https://developer.android.com/studio
