## Contexto

Estás actuando como **Senior Product Owner, Business Analyst y Agile Coach**, especializado en descomponer Product Requirements Documents (PRD.md adjunto) en Product Backlogs de alta calidad.
Vas a recibir el PRD del producto **FlowSync**, una aplicación web que sincroniza tareas personales con Google Calendar.
**El objetivo del MVP** es validar que los usuarios adopten un gestor de tareas que elimine la necesidad de mantener sincronizados manualmente una lista de tareas y un calendario.
El usuario objetivo es un profesional que utiliza Google Calendar diariamente y desea gestionar sus tareas desde un único lugar.
Trabaja únicamente con la información contenida en el PRD.

**Stack técnico**: AdonisJS 7 + TypeScript (backend) · React 19 + Vite + Tailwind (frontend) · Google Calendar API con OAuth 2.0.

**Alcance del MVP** (lo único que debes cubrir):
- Registro y autenticación de usuarios
- CRUD completo de tareas con estados
- Filtrado y organización básica de tareas
- Exportación de tareas a CSV
- Sincronización con Google Calendar (lectura y escritura)

## Tu tarea

Lee el PRD adjunto y extrae únicamente las user stories que correspondan a funcionalidades explícitamente descritas en el documento. No inventes features, no añadas comportamientos que no estén en el PRD, y no incluyas funcionalidades marcadas como out of scope.

## Formato de cada story

Cada story debe seguir exactamente esta estructura:

**US-[número]: [título corto]**
Como [rol], quiero [acción], para [beneficio].

**Criterios de aceptación:**
- **Dado que** [contexto inicial], **cuando** [acción del usuario o evento], **entonces** [resultado esperado y verificable].
- *(repite entre 3 y 5 criterios por story; cada uno debe ser concreto y testeable, no genérico)*

## Reglas de los criterios de aceptación

- Cada criterio debe poder verificarse en un test funcional o de integración.
- Nada de criterios vagos como "el sistema funciona correctamente" o "el usuario tiene una buena experiencia".
- Incluye casos de error donde el PRD los mencione (email ya registrado, contraseña corta, campos obligatorios, fallos de sincronización, etc.).

## Agrupación

Organiza las stories en épicas. Usa exactamente estas épicas (en este orden), e incluye solo las que tengan al menos una story:

1. **Autenticación y gestión de cuenta**
2. **Gestión de tareas (CRUD)**
3. **Organización y filtrado**
4. **Exportación**
5. **Sincronización con Google Calendar**

Dentro de cada épica, numera las stories de forma correlativa (US-01, US-02, …).

## Restricciones finales

- Rol permitido: solo "usuario" o "usuario autenticado" (el MVP no tiene roles distintos).
- No incluyas stories de administración, equipos, notificaciones push, app móvil nativa, etiquetas, subtareas ni recordatorios configurables: están explícitamente fuera del MVP.
- **Si el PRD deja algo ambiguo (p. ej., el criterio exacto de ordenación de tareas), redacta la story con el comportamiento descrito y añade una nota `> Pendiente de definir en refinamiento: [pregunta concreta]` justo debajo.**
- No inventes:
  - endpoints
  - tablas
  - modelos de datos
  - arquitectura
  - validaciones no descritas
  - reglas de negocio inexistentes
  - tareas de implementación
  - refactorizaciones
- No generes subtareas de desarrollo.
- No generes estimaciones.
- No asumas comportamiento implícito.

# Verificación

Antes de responder verifica que:

- Todas las historias provienen del PRD.
- Solo incluyes funcionalidades del MVP.
- No agregaste funcionalidades inexistentes.
- Todas las historias siguen el formato **Como / Quiero / Para**.
- Todas tienen entre **3 y 5** Acceptance Criteria en formato **Given / When / Then**.


