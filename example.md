# Guía Práctica de Implementación: Calculadora Científica Web
> **Ejemplo de ciclo completo usando ACE Framework**

Este archivo es una guía paso a paso ("Walkthrough") de cómo construir un proyecto sencillo (una Calculadora Científica con HTML, CSS y JS) utilizando la metodología ACE. Úsalo como plantilla para tus propios proyectos.

---

## 0. Preparación
Asumimos que ya has ejecutado `npx create-ace-framework .` y tienes la estructura de carpetas básica (`.ace/`, `docs/`, etc.).

---

## FASE 1: Inicialización de Sesión
**Objetivo:** Cargar el "cerebro" del framework en la memoria de la IA.

**🧑‍💻 Tú (Prompt):**
> "Estoy iniciando una sesión con ACE-Framework. Por favor:
> 1. Lee `.aceconfig` para la configuración del proyecto.
> 2. Lee `.ace/roles/roles.md` para entender tus roles disponibles.
> 3. Lee `docs/context/ACTIVE_CONTEXT.md` para ver el estado actual.
> Confirma que entiendes el contexto y espera instrucciones."

**🤖 IA (Respuesta Esperada):**
> "Entendido. He cargado la configuración y los roles. El contexto activo está vacío/inicializado. Estoy listo. ¿Cuál es el objetivo de esta sesión?"

---

## FASE 2: ANALYZE & DISCUSS (Rol: Arquitecto)
**Objetivo:** Definir qué vamos a construir y cómo, antes de escribir código.

**🧑‍💻 Tú (Prompt):**
> "Actúa como **Architect**. Entra en modo **ANALYZE**.
> Quiero crear una Calculadora Científica sencilla pero moderna usando HTML, CSS y Vanilla JS.
> 
> Requisitos:
> - Diseño oscuro (Dark mode).
> - Operaciones básicas (+, -, *, /) y científicas (sin, cos, tan, sqrt, pow).
> - Debe ser responsive.
> - Todo en un solo archivo `index.html` o separado en 3 archivos (prefiero separados).
> 
> Analiza esto y hazme preguntas si necesitas aclarar algo (Fase DISCUSS)."

**🤖 IA (Respuesta Esperada):**
> "Analizando... Aquí hay algunas dudas para definir en la fase DISCUSS:
> 1. ¿Necesitas historial de operaciones?
> 2. ¿Usamos alguna librería CSS como Tailwind o CSS puro?
> 3. ¿Cómo manejamos los errores de punto flotante de JS?"

**🧑‍💻 Tú (Respuesta):**
> "1. No historial.
> 2. CSS puro (CSS Grid).
> 3. Usa `toFixed(8)` para mitigar errores visuales."

**🧑‍💻 Tú (Cierre de Fase):**
> "Perfecto. Actualiza `docs/context/ACTIVE_CONTEXT.md` con estas decisiones."

---

## FASE 3: PLAN (Rol: Arquitecto)
**Objetivo:** Crear un mapa de ruta paso a paso.

**🧑‍💻 Tú (Prompt):**
> "Mantente como **Architect**. Entra en modo **PLAN**.
> Genera el archivo `docs/planning/implementation_plan.md`.
> Divide el trabajo en tareas atómicas (muy pequeñas).
> Usa el formato XML o lista numerada estricta."

**📄 Resultado generado por la IA (`docs/planning/implementation_plan.md`):**

```markdown
# Plan de Implementación: Calculadora Científica

## Tareas
1. **[Estructura]** Crear `index.html` con la estructura semántica y contenedores (Display, Keypad).
2. **[Estilos]** Crear `style.css` con variables CSS para colores oscuros y CSS Grid para el teclado.
3. **[Lógica Base]** Crear `script.js` con funciones para capturar clics y actualizar el display.
4. **[Lógica Ops]** Implementar operaciones matemáticas básicas y manejo de estado (current, previous operand).
5. **[Lógica Científica]** Implementar funciones Math (sin, cos, etc.).
6. **[Refinamiento]** Manejo de errores (división por 0) y teclado físico (event listener).
```

**🧑‍💻 Tú (Aprobación):**
> "El plan se ve bien. Aprobado."

---

## FASE 4: EXECUTE (Rol: Desarrollador)
**Objetivo:** Escribir el código siguiendo el plan, paso a paso. **NO** dejes que la IA haga todo de golpe.

### Tarea 1: Estructura HTML
**🧑‍💻 Tú (Prompt):**
> "Cambia a rol **Developer**. Modo **EXECUTION**.
> Vamos a realizar la **Tarea 1** del plan: Crear `index.html`.
> Solo haz el HTML, no incluyas CSS ni JS aún (usa placeholders)."

**🤖 IA:** *Genera el código de index.html*

### Tarea 2: Estilos CSS
**🧑‍💻 Tú (Prompt):**
> "Tarea 1 completada. Márcala en `docs/planning/task_checklist.md` (si existe) o en tu memoria.
> Ahora realiza la **Tarea 2**: Crear `style.css`.
> Asegúrate de usar CSS Grid como acordamos."

**🤖 IA:** *Genera el código de style.css*

### Tarea 3 y 4: Lógica JS
**🧑‍💻 Tú (Prompt):**
> "Bien. Ahora **Tarea 3 y 4 juntas**: Crea `script.js` con la lógica básica y las operaciones aritméticas.
> Recuerda vincular el script en el HTML si no lo hiciste."

**🤖 IA:** *Genera el código de script.js*

---

## FASE 5: VERIFY (Rol: QA Engineer)
**Objetivo:** Asegurar que funciona y no rompe nada.

**🧑‍💻 Tú (Prompt):**
> "Cambia a rol **QA Engineer**. Modo **VERIFICATION**.
> 1. Revisa el código generado buscando errores comunes (ej: eval() peligroso, variables globales).
> 2. Genera una lista rápida de pruebas manuales que debo hacer yo en el navegador."

**🤖 IA (Respuesta Esperada):**
> "Revisión completada:
> - El código usa `eval()` (mala práctica) -> Sugiero cambiarlo por una función de parseo segura.
> 
> Plan de Pruebas Manuales:
> 1. Probar `10 / 0` (Debe decir 'Error' o 'Infinity').
> 2. Probar `0.1 + 0.2` (Debe dar 0.3, no 0.300000004).
> 3. Probar funciones científicas encadenadas."

**🧑‍💻 Tú (Si hay correcciones):**
> "Developer, corrige el uso de `eval()` según la recomendación de QA."

---

## FASE 6: Cierre de Sesión
**Objetivo:** Guardar el estado para que mañana (o en 1 hora) la IA sepa dónde nos quedamos.

**🧑‍💻 Tú (Prompt):**
> "Hemos terminado por hoy. Funciona perfecto.
> Actualiza `docs/context/ACTIVE_CONTEXT.md`:
> - Marca todas las tareas como completadas.
> - Estado actual: Funcional v1.0.
> - Próximos pasos: Ninguno por ahora.
> Haz un resumen final."

**📄 Resultado (`docs/context/ACTIVE_CONTEXT.md` actualizado):**
```markdown
# Active Context
## Estado Actual
Calculadora científica v1.0 completada y funcional.
Archivos creados: index.html, style.css, script.js.

## Últimos cambios
- Implementación de UI Dark Mode.
- Lógica JS sin usar eval().

## Próximos Pasos
- (Vacío)
```

---

## Resumen de Comandos Rápidos ("Cheatsheet")

| Acción | Prompt |
| :--- | :--- |
| **Empezar** | "Lee `.aceconfig` y `ACTIVE_CONTEXT.md`. Inicio sesión." |
| **Planear** | "Rol Architect. Modo PLAN. Crea un plan de implementación para [X]." |
| **Codificar** | "Rol Developer. Ejecuta la Tarea [N] del plan." |
| **Revisar** | "Rol QA. Analiza el código buscando bugs o problemas de seguridad." |
| **Guardar** | "Actualiza `ACTIVE_CONTEXT.md` con el progreso." |
