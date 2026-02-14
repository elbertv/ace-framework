# Ace Framework: Guía Informativa Completa

## ¿Qué es Ace Framework?

**Ace Framework (AI-assisted Code Engineering)** es un estándar riguroso e independiente del IDE diseñado para equipos de desarrollo profesional que utilizan agentes de Inteligencia Artificial (como Claude, Gemini, ChatGPT, Cursor, etc.). 

A diferencia de un uso casual de la IA, Ace Framework trata las interacciones con la IA como **transacciones estructuradas**, asegurando consistencia, calidad y trazabilidad en todo el proceso de ingeniería de software.

## Propósito y Filosofía

El propósito principal es eliminar el "caos" y la falta de estructura que a menudo ocurre al usar asistentes de IA. Sus pilares fundamentales son:

1.  **Rigurosidad**: No se escribe código sin un plan previo.
2.  **Contexto Persistente**: Evita que la IA "olvide" lo que se ha decidido en sesiones anteriores.
3.  **Seguridad**: Protege el código contra regresiones (errores que vuelven a aparecer).
4.  **Roles Especializados**: Divide el trabajo en roles como Arquitecto, Desarrollador y QA.

---

## ¿Cómo funciona? El Ciclo BMAD

Ace Framework utiliza la metodología **BMAD** (*Breakthrough Method for Agile AI-Driven Development*), que divide cada tarea en 5 fases obligatorias:

1.  **ANALYZE (Analizar)**: El Arquitecto lee los requisitos y define las restricciones.
2.  **DISCUSS (Discutir)**: Se alinean las preferencias ("Soft requirements") con el usuario antes de planificar.
3.  **PLAN (Planificar)**: Se crea un plan de implementación detallado y atómico.
4.  **EXECUTE (Ejecutar)**: El Desarrollador implementa el código tarea por tarea, con tests incluidos.
5.  **VERIFY (Verificar)**: El QA Engineer valida que todo funcione y cumpla los estándares.

Si algo falla, se entra en modo **INCIDENT** para realizar un análisis de causa raíz (RCA) y prevenir que el error se repita.

---

## Estructura del Framework (El "Cerebro")

El framework se organiza principalmente en dos carpetas clave:

### 1. Directorio `.ace/` (Centro de Control)
*   **`knowledge/`**: Diccionario de términos y reglas de negocio del proyecto.
*   **`prompts/`**: Plantillas de prompts optimizadas ("Golden Prompts").
*   **`roles/`**: Definiciones de los 7 roles (Arquitecto, Desarrollador, QA, etc.).
*   **`skills/`**: Guías de procedimientos para tareas específicas (ej. diseño de APIs, bases de datos).
*   **`standards/`**: Reglas innegociables de código, seguridad y arquitectura.

### 2. Directorio `docs/` (Memoria de Sesión)
*   **`context/ACTIVE_CONTEXT.md`**: El archivo más importante. Guarda el estado actual de la sesión, objetivos y pasos siguientes.
*   **`adr/`**: (Architecture Decision Records) Registro de todas las decisiones técnicas importantes.
*   **`planning/`**: Planes de implementación y listas de tareas actuales.
*   **`rca/`**: Análisis de errores y "Guards" (protecciones) contra regresiones.

---

## Cómo Instalarlo

Para usar Ace Framework en un proyecto nuevo o existente, puedes usar la herramienta CLI oficial:

### Usando npx (Recomendado)
Puedes crear un proyecto nuevo o añadir el framework al directorio actual sin instalar nada permanentemente:

```bash
# Para un proyecto nuevo
npx create-ace-framework mi-proyecto

# Para el directorio actual
npx create-ace-framework .
```

### Instalación Global
Si prefieres tener el comando siempre disponible:

```bash
npm install -g create-ace-framework

# Luego úsalo directamente
create-ace-framework
```

**Requisitos:** Node.js 16 o superior y Git.

---

## Cómo empezar a usarlo (Guía Rápida)

Una vez instalado, sigue estos pasos para tu primera sesión con un asistente de IA:

1.  **Carga el contexto**: Copia y pega esto al inicio de tu chat con la IA:
    > "Estoy iniciando una sesión con ACE-Framework. Por favor, lee `.aceconfig`, `.ace/roles/roles.md` y `docs/context/ACTIVE_CONTEXT.md` para entender el estado actual y las reglas. Confirma que entiendes y espera instrucciones."

2.  **Define tu objetivo**: Indica qué quieres construir.
    > "Cambia al rol de Arquitecto y entra en modo ANALYZE. Quiero implementar un sistema de autenticación JWT."

3.  **Sigue el ciclo**:
    *   Deja que la IA analice y te pregunte preferencias (Discuss).
    *   Aprueba el plan de implementación que genere en `docs/planning/`.
    *   Cambia al rol de Desarrollador para que escriba el código.
    *   Finaliza con el QA para verificar los tests.

4.  **Cierra la sesión**: Antes de terminar el chat, pide a la IA:
    > "Actualiza `docs/context/ACTIVE_CONTEXT.md` con los avances de hoy, los bloqueos y los pasos a seguir."

---

## Documentación Adicional
*   **`USER_GUIDE.md`**: Guía práctica para el día a día.
*   **`ACE-SPEC.md`**: Especificación técnica completa del framework.
*   **`README.md`**: Resumen rápido de características.
