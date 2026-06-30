Product Backlog — FlowSync MVP
Épica 1: Autenticación y gestión de cuenta
US-01: Registro de cuenta con email y contraseña
Como usuario, quiero crear una cuenta con mi email y contraseña, para acceder a FlowSync con credenciales propias.

Criterios de aceptación:

Dado que soy un visitante sin cuenta, cuando introduzco un email válido y una contraseña de al menos 8 caracteres y envío el formulario, entonces mi cuenta se crea y soy redirigido a la pantalla de bienvenida.
Dado que intento registrarme, cuando introduzco una contraseña con menos de 8 caracteres, entonces el sistema muestra un mensaje de error indicando que la contraseña debe tener al menos 8 caracteres y no crea la cuenta.
Dado que intento registrarme, cuando introduzco un email que ya está registrado en el sistema, entonces el sistema muestra un mensaje indicando que el email ya existe y ofrece un enlace o acción para ir al inicio de sesión.
Dado que mi registro es exitoso, cuando llego a la pantalla de bienvenida, entonces veo una explicación en una frase de qué hace FlowSync y una invitación a crear mi primera tarea.
US-02: Inicio de sesión
Como usuario, quiero iniciar sesión con mi email y contraseña, para acceder a mis tareas.

Criterios de aceptación:

Dado que tengo una cuenta registrada, cuando introduzco mi email y contraseña correctos y envío el formulario, entonces inicio sesión y accedo a la aplicación con una sesión activa mediante token de acceso.
Dado que intento iniciar sesión, cuando introduzco un email o contraseña incorrectos, entonces el sistema muestra un mensaje de error comprensible y no concede acceso.
Dado que tengo una sesión activa, cuando regreso a la aplicación sin haber cerrado sesión, entonces mi sesión sigue activa y no se me pide volver a autenticarme.
US-03: Cierre de sesión
Como usuario autenticado, quiero cerrar sesión, para finalizar mi sesión de forma segura.

Criterios de aceptación:

Dado que tengo una sesión activa, cuando ejecuto la acción de cerrar sesión, entonces mi sesión se termina y soy redirigido a la pantalla de inicio de sesión (o equivalente pública).
Dado que he cerrado sesión, cuando intento acceder a una pantalla que requiere autenticación, entonces el sistema me redirige a la pantalla de inicio de sesión en lugar de mostrarme los datos.
Épica 2: Gestión de tareas (CRUD)
US-04: Crear una tarea
Como usuario autenticado, quiero crear una tarea indicando al menos un título, para registrar un pendiente en FlowSync.

Criterios de aceptación:

Dado que estoy en la aplicación, cuando creo una tarea con título, descripción y fecha límite, entonces la tarea aparece en mi listado con todos los campos introducidos y estado pending.
Dado que creo una tarea, cuando solo proporciono un título (sin descripción ni fecha límite), entonces la tarea se crea correctamente con estado pending y los campos opcionales vacíos.
Dado que intento crear una tarea, cuando no proporciono ningún título, entonces el sistema muestra un error indicando que el título es obligatorio y no crea la tarea.
Dado que creo cualquier tarea, cuando la tarea se guarda correctamente, entonces su estado inicial es pending.
US-05: Ver el listado de tareas
Como usuario autenticado, quiero ver el listado de mis tareas, para conocer mis pendientes actuales.

Criterios de aceptación:

Dado que tengo tareas creadas, cuando accedo al listado, entonces veo únicamente mis propias tareas (ningún dato de otros usuarios es visible).
Dado que accedo al listado, cuando no tengo ninguna tarea (cuenta nueva o todas archivadas), entonces veo un estado vacío con una invitación a crear la primera tarea.
Dado que tengo tareas, cuando accedo al listado, entonces las tareas se muestran ordenadas de forma que las más relevantes para el día actual aparecen primero.
Pendiente de definir en refinamiento: ¿Cuál es el criterio exacto de ordenación "más relevantes para hoy"? (¿por fecha límite ascendente, por estado, o combinación de ambos?)

US-06: Editar una tarea
Como usuario autenticado, quiero editar cualquier campo de una tarea existente, para mantener mis tareas actualizadas.

Criterios de aceptación:

Dado que tengo una tarea existente, cuando modifico su título, descripción o fecha límite y guardo los cambios, entonces el listado refleja los nuevos valores.
Dado que edito una tarea, cuando elimino el título dejándolo vacío e intento guardar, entonces el sistema muestra un error indicando que el título es obligatorio y no guarda los cambios.
Dado que edito una tarea con fecha límite, cuando guardo el cambio de fecha, entonces la tarea queda actualizada con la nueva fecha.
US-07: Borrar una tarea
Como usuario autenticado, quiero borrar una tarea, para eliminar pendientes que ya no son relevantes.

Criterios de aceptación:

Dado que tengo una tarea existente, cuando ejecuto la acción de borrarla y confirmo, entonces la tarea desaparece de mi listado y ya no es accesible.
Dado que borro una tarea, cuando la eliminación se completa, entonces el resto de mis tareas permanecen sin cambios.
US-08: Cambiar el estado de una tarea
Como usuario autenticado, quiero cambiar el estado de una tarea entre pending, completed y archived, para reflejar el progreso de mis pendientes.

Criterios de aceptación:

Dado que tengo una tarea en estado pending, cuando la marco como completada, entonces su estado cambia a completed y el cambio se refleja en el listado.
Dado que tengo una tarea en cualquier estado, cuando la archivo, entonces su estado cambia a archived.
Dado que tengo una tarea en estado completed o archived, cuando la revierto a pending, entonces su estado cambia a pending.
Épica 3: Organización y filtrado
US-09: Filtrar tareas por estado
Como usuario autenticado, quiero filtrar mis tareas por estado, para ver únicamente las tareas que me interesan en un momento dado.

Criterios de aceptación:

Dado que tengo tareas con distintos estados, cuando aplico el filtro pending, entonces solo se muestran las tareas en estado pending.
Dado que tengo tareas con distintos estados, cuando aplico el filtro completed, entonces solo se muestran las tareas en estado completed.
Dado que tengo tareas con distintos estados, cuando aplico el filtro archived, entonces solo se muestran las tareas en estado archived.
Dado que tengo un filtro activo y no hay tareas que coincidan, cuando se aplica el filtro, entonces veo el estado vacío correspondiente (sin tareas).
Épica 4: Exportación
US-10: Exportar tareas a CSV
Como usuario autenticado, quiero exportar mis tareas a un archivo CSV, para llevarme mis datos fuera de FlowSync.

Criterios de aceptación:

Dado que tengo tareas creadas, cuando ejecuto la acción de exportar, entonces se descarga un archivo CSV que contiene, como mínimo, título, descripción, estado y fecha límite de cada tarea.
Dado que exporto mis tareas, cuando el archivo se genera, entonces el CSV incluye únicamente mis propias tareas, no las de otros usuarios.
Dado que no tengo ninguna tarea, cuando ejecuto la acción de exportar, entonces el sistema genera un CSV vacío (solo con cabeceras) o informa de que no hay datos a exportar.
Épica 5: Sincronización con Google Calendar
US-11: Conectar cuenta de Google
Como usuario autenticado, quiero conectar mi cuenta de Google a FlowSync mediante OAuth, para habilitar la sincronización con mi Google Calendar.

Criterios de aceptación:

Dado que no tengo Google conectado, cuando inicio el flujo de conexión con Google, entonces soy redirigido al flujo de autorización OAuth de Google y, tras autorizarlo, vuelvo a FlowSync con la conexión establecida.
Dado que completo la autorización OAuth, cuando regreso a FlowSync, entonces el sistema almacena de forma segura el token de Google y la conexión queda activa.
Dado que ya tengo Google conectado, cuando accedo a la configuración, entonces puedo ver que la cuenta está conectada.
US-12: Sincronizar tareas con fecha límite como eventos en Google Calendar
Como usuario autenticado, quiero que mis tareas con fecha límite aparezcan automáticamente como eventos en mi Google Calendar, para ver mis pendientes y mi agenda en un solo lugar.

Criterios de aceptación:

Dado que tengo Google Calendar conectado, cuando creo una tarea con fecha límite, entonces se crea un evento correspondiente en mi Google Calendar.
Dado que tengo Google Calendar conectado, cuando creo una tarea sin fecha límite, entonces no se crea ningún evento en Google Calendar.
Dado que tengo Google Calendar conectado y la API de Google no está disponible en el momento de crear la tarea, cuando la operación de sincronización falla, entonces la tarea se guarda correctamente en FlowSync, se registra el fallo en los logs y la sincronización se reintenta posteriormente.
Pendiente de definir en refinamiento: ¿A qué hora exacta del día se crea el evento cuando la tarea solo tiene fecha límite (sin hora)? Esto afecta directamente a la experiencia del usuario en zonas horarias distintas.

US-13: Actualizar evento en Google Calendar al cambiar la fecha de una tarea
Como usuario autenticado, quiero que al cambiar la fecha límite de una tarea el evento de Google Calendar se actualice automáticamente, para mantener ambas herramientas sincronizadas.

Criterios de aceptación:

Dado que tengo Google Calendar conectado y una tarea con un evento en Calendar, cuando cambio la fecha límite de la tarea, entonces el evento correspondiente en Google Calendar se actualiza con la nueva fecha.
Dado que tengo Google Calendar conectado y una tarea con fecha límite, cuando elimino la fecha límite de la tarea (la dejo sin fecha), entonces el evento correspondiente en Google Calendar se elimina.
Dado que la API de Google no está disponible al intentar actualizar el evento, cuando ocurre el fallo de sincronización, entonces la tarea se actualiza en FlowSync, el fallo queda registrado en los logs y se reintenta la sincronización posteriormente.
US-14: Eliminar evento de Google Calendar al completar o borrar una tarea
Como usuario autenticado, quiero que al completar o borrar una tarea su evento en Google Calendar se elimine o actualice en consecuencia, para que mi calendario no acumule eventos obsoletos.

Criterios de aceptación:

Dado que tengo Google Calendar conectado y una tarea con evento en Calendar, cuando marco la tarea como completada, entonces el evento correspondiente en Google Calendar se elimina o se marca según corresponda.
Dado que tengo Google Calendar conectado y una tarea con evento en Calendar, cuando borro la tarea, entonces el evento correspondiente en Google Calendar se elimina.
Dado que la API de Google no está disponible al intentar eliminar el evento, cuando ocurre el fallo, entonces la tarea se actualiza o elimina correctamente en FlowSync, el fallo queda registrado en los logs y se reintenta la sincronización posteriormente.
Pendiente de definir en refinamiento: ¿"Marcar según corresponda" al completar una tarea significa eliminar el evento o marcarlo de alguna forma en Calendar (p. ej., tachar el título)? El PRD lo deja abierto.

US-15: Desconectar cuenta de Google
Como usuario autenticado, quiero desconectar mi cuenta de Google de FlowSync, para dejar de sincronizar mis tareas con Google Calendar sin perder los datos ya guardados.

Criterios de aceptación:

Dado que tengo Google Calendar conectado, cuando ejecuto la acción de desconectar mi cuenta de Google, entonces FlowSync deja de sincronizar tareas con Google Calendar y el token de Google se invalida o elimina del sistema.
Dado que desconecto mi cuenta de Google, cuando la desconexión se completa, entonces todas mis tareas existentes en FlowSync se conservan intactas.
Dado que he desconectado Google, cuando creo o edito una tarea con fecha límite, entonces no se realiza ninguna operación de sincronización con Google Calendar.