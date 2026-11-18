FAYE – INSTALACIÓN Y ACTUALIZACIÓN EN LA CENTRAL
================================================

Faye es un solo archivo (Faye.exe). No se instala nada: incluye todo lo necesario.
Requisito: Windows 10 u 11 de 64 bits.


1. PRIMERA VEZ
--------------
1. Crea la carpeta C:\Faye
   (no uses "Archivos de programa": Faye necesita escribir su carpeta "data").
2. Copia Faye.exe dentro de C:\Faye
3. Abre Faye.exe con doble clic.
   - Si aparece "Windows protegió su PC": Más información -> Ejecutar de todas formas.
4. Configuración inicial: ingresa la URL del Web App (/exec) y el token de Faye.
   Se guardan cifrados y solo sirven en este equipo.
5. Aparece el ícono rojo con una "F" junto al reloj.
   Si no se ve, revisa la flecha "^" de la barra de tareas y arrástralo afuera.
6. Clic derecho en el ícono -> "Probar conexión y reenviar".
7. Clic derecho -> "Iniciar con Windows". La primera vez pide CREAR el PIN de administrador.
8. Clic derecho -> "Horarios…" y revisa que la vista previa muestre los reportes esperados.

Revisa también en Windows:
- Configuración -> Sistema -> Notificaciones: activadas, y "No molestar" desactivado.
- Configuración -> Sistema -> Energía: el equipo no debe suspenderse.


2. ACTUALIZAR (DESDE LA VERSIÓN 1.1.0)
--------------------------------------
Faye NO busca actualizaciones por su cuenta: se actualiza solo cuando alguien lo pide.
1. Clic derecho en el ícono -> "Actualizar…" (pide el PIN).
2. Si hay una versión nueva, muestra cuál es y pregunta si instalarla.
3. La descarga y verifica que el archivo esté completo y sea Faye.
4. Guarda la versión actual como Faye-anterior.exe, se cierra y se abre la nueva.
5. Aparece el aviso "Faye se actualizó a la versión X".
   Si la nueva no inicia en 90 segundos, Faye vuelve solo a la versión anterior.

No se puede actualizar con un reporte abierto ni a menos de 3 minutos del próximo reporte:
Faye avisa y se vuelve a intentar después.
La configuración, el PIN, los horarios y los pendientes no se tocan (están en C:\Faye\data).
La primera línea del menú muestra la versión instalada, y la columna "Versión" de la hoja
de reportes muestra qué versión envió cada reporte.

Requisito: el PC debe poder conectarse a github.com.


3. VOLVER A LA VERSIÓN ANTERIOR (SI ALGO FALLA)
-----------------------------------------------
Si la versión nueva no inicia, Faye vuelve solo a la anterior.
Si inicia pero algo funciona mal, se hace a mano:
1. Clic derecho en el ícono -> Salir (pide el PIN).
   Si no responde: Administrador de tareas -> Faye -> Finalizar tarea.
2. En C:\Faye, cambia el nombre de Faye.exe a Faye-descartada.exe
3. Cambia el nombre de Faye-anterior.exe a Faye.exe
4. Ábrelo con doble clic.
Mientras no se publique una versión más nueva, "Actualizar…" volverá a ofrecer la descartada:
no la instales hasta corregirla.

Actualización manual (sin internet): Salir (PIN), cambia el nombre de Faye.exe a
Faye-anterior.exe, copia el Faye.exe nuevo en C:\Faye y ábrelo.
Historial de actualizaciones: C:\Faye\data\update\historial.log


4. PROBLEMAS FRECUENTES
-----------------------
- Pide la configuración inicial otra vez:
  la carpeta data se copió desde otro equipo o usuario. Ingresa de nuevo URL y token.
- "Nube: sin conexión": revisa internet. Los reportes quedan guardados en
  C:\Faye\data\outbox y se envían solos al volver la conexión.
- No aparecen los nombres correctos: edítalos en la hoja "Operadores" de Google
  (columna Activo marcada). Faye los actualiza cada 30 minutos o con
  "Probar conexión y reenviar".
- Olvidé el PIN: cierra Faye desde el Administrador de tareas, abre
  C:\Faye\data\config.json con el Bloc de notas, borra los valores de
  "adminPinHash" y "adminPinSalt" (deja ""), guarda y abre Faye.
- Restaurar una configuración anterior: cierra Faye y copia un archivo de
  C:\Faye\data\backups sobre C:\Faye\data\config.json.


5. NO HACER
-----------
- No compartir capturas de config.json ni del token.
- No poner "testMode": true en la central.
- No borrar la carpeta C:\Faye\data (tiene la configuración y los pendientes).
- No borrar Faye-anterior.exe: es la versión de respaldo.
