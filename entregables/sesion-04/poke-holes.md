# Prompt poke-holes
Aquí tienes esta user story con sus criterios de aceptación:

"US-04: Crear una tarea
Como usuario autenticado, quiero crear una tarea indicando al menos un título, para registrar un pendiente en FlowSync.

Criterios de aceptación:
- Dado que estoy en la aplicación, cuando creo una tarea con título, descripción y fecha límite, entonces la tarea aparece en mi listado con todos los campos introducidos y estado pending.
- Dado que creo una tarea, cuando solo proporciono un título (sin descripción ni fecha límite), entonces la tarea se crea correctamente con estado pending y los campos opcionales vacíos.
- Dado que intento crear una tarea, cuando no proporciono ningún título, entonces el sistema muestra un error indicando que el título es obligatorio y no crea la tarea.
- Dado que creo cualquier tarea, cuando la tarea se guarda correctamente, entonces su estado inicial es pending."

Tu tarea: identifica edge cases, supuestos implícitos, escenarios faltantes, y dependencias o riesgos no mencionados. No reescribas la story, solo lista lo que falta o lo que asumiste.

# Hallazgos 
- Validación de campos de Título con solo espacios en blanco, número máximo de caracteres y Fecha límite en el pasado no incluida, parece algo simple, pero representa manejo de errores y reducción de futuros bugs.
- Se asumió que solo descripción y fecha límite son los únicos campos opcionales, pero si el objetivo es sincronizar con un calendario, la fecha debería ser obligatoria.
- Formato y zona horaria de la fecha límite, este es crítico debido a que se está sincronizando con un calendario debe estar definido, hace parte de las funcionalidades core de FlowSync.
- Comportamiento tras guardar, me parece importante dado que afecta la experiencia de usuario y confirmación de tarea creada.