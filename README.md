# Cuestionario Interactivo de Ciberseguridad

Este es un simple cuestionario interactivo creado con HTML, CSS (Tailwind) y JavaScript. Permite presentar preguntas de opción única, opción múltiple y de unir conceptos.

## Características

- Preguntas de opción única
- Preguntas de opción múltiple
- Preguntas de unir conceptos
- Barajado aleatorio de preguntas y opciones
- Retroalimentación instantánea
- Puntuación final

## Cómo Usar

1. **Guardar el archivo**: Asegúrate de tener el archivo `index.html` (que contiene el código del cuestionario) guardado en tu computadora.
2. **Abrir en el navegador**: Haz doble clic en el archivo `index.html` o ábrelo usando la opción "Abrir archivo..." de tu navegador web preferido (como Chrome, Firefox, Edge, etc.).
3. **Responder el cuestionario**: Interactúa con las preguntas y haz clic en "Enviar Respuestas" al finalizar.
4. **Ver resultados**: Se mostrará tu puntuación y la retroalimentación para cada pregunta.
5. **Reintentar**: Puedes usar el botón "Intentar de Nuevo" para volver a realizar el cuestionario (las preguntas y opciones se barajarán de nuevo).

## Personalización de Preguntas

Actualmente, las preguntas están definidas directamente dentro del archivo `index.html`, en una variable JavaScript llamada `quizData` dentro de la etiqueta `<script>`.

```javascript
// --- Quiz Data ---
const quizData = [
    {
        type: 'single',
        question: '¿Pregunta de opción única?',
        options: ['Opción A', 'Opción B', 'Respuesta Correcta'],
        correctAnswer: 'Respuesta Correcta'
    },
    // ... más preguntas ...
];
// ... Resto del código ...
```

Puedes editar esta variable `quizData` directamente para cambiar, añadir o eliminar preguntas, siguiendo el formato explicado anteriormente.

## Usar un Archivo JSON Externo para las Preguntas

Para mejor organización, mantenimiento y reutilización, puedes cargar las preguntas desde un archivo JSON externo en lugar de definirlas en el HTML.

### Pasos

1. **Crear preguntas.json**:
    - Crea un archivo llamado `preguntas.json` en la misma carpeta que `index.html`.
    - Dentro, usa la misma estructura que el array `quizData` original, pero con sintaxis JSON (comillas dobles para claves y strings, sin comentarios).

    Ejemplo `preguntas.json`:

    ```json
    [
        {
        "type": "single",
        "question": "¿Cuál es el objetivo principal de un CSIRT?",
        "options": ["Opción A", "Respuesta Correcta"],
        "correctAnswer": "Respuesta Correcta"
        },
        ...
    ]
    ```

2. **Modificar index.html**:
   - En la sección `<script>`, elimina o comenta la variable `const quizData = [...]`.

3. **Probar con el Cuestionario**:
   - Abrir `index.html` directamente en un navegador

## Tipos de Preguntas

### Opción Única

```javascript
{
    type: 'single',
    question: '¿Pregunta de ejemplo?',
    options: ['Opción A', 'Opción B', 'Respuesta Correcta'],
    correctAnswer: 'Respuesta Correcta'
}
```

### Opción Múltiple

```javascript
{
    type: 'multiple',
    question: '¿Pregunta de selección múltiple?',
    options: ['Opción A', 'Opción Correcta 1', 'Opción Correcta 2', 'Opción D'],
    correctAnswer: ['Opción Correcta 1', 'Opción Correcta 2']
}
```

### Unir Conceptos

```javascript
{
    type: 'matching',
    question: 'Une los conceptos relacionados',
    pairs: [
        { left: 'Concepto A', right: 'Definición A' },
        { left: 'Concepto B', right: 'Definición B' },
        { left: 'Concepto C', right: 'Definición C' }
    ]
}
```
