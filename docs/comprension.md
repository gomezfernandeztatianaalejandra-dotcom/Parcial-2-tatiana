# Comprensión del diseño — Enunciado C
**Nombre:Tatiana Alejandra Gomez Fernandez 
**Fecha:19/10/2026

Responde con tus palabras, basándote en `docs/UML-final.md`. Respuestas
concisas (2–4 líneas por pregunta). Evidencia que entendiste el contrato
**antes** de programar.

---

### 1. Herencia y polimorfismo
¿Por qué `Curso` es una clase abstracta y no concreta? Menciona qué método
obliga a cada subclase a implementar y qué gana el sistema con eso.

> _Tu respuesta: Es abstracta porque no existen cursos genéricos. Obliga a implementar dificultad esperada, permitiendo que el sistema trate a todas las materias por igual pero calcule su dificultad según su tipo.

---

### 2. Composición vs. agregación
Explica la diferencia entre `PlanEstudios ◆— Curso` (composición) y
`Facultad ◇— PlanEstudios` (agregación). ¿Qué pasaría con los cursos si se
elimina el plan? ¿Y con los planes si se elimina la facultad?

> _Tu respuesta: Si eliminas el planEstudios, sus cursos desaparecen composición, si eliminas la facultad, los planes de estudio siguen existiendo agregación

---

### 3. Asociación
En `Estudiante — Curso`, ¿quién es dueño de quién? ¿Por qué se modela como
N:M y no como composición?

> _Tu respuesta:Ninguno es dueño de nadie, Un estudiante ve muchos cursos y a un curso van muchos estudiantes, si el estudiante se retira, el curso no se elimina.

---

### 4. Dependencia
¿Por qué `Recomendador` **depende** de `HistorialAcademico` en lugar de
**tenerlo** como atributo? ¿Qué ventaja tiene pasar el servicio como
parámetro?

> _Tu respuesta:Para que el Recomendador no esté atado a un solo estudiante y pueda procesar múltiples historiales libremente, la ventaja es que se vuelve más flexible y reutilizable.

---

### 5. Listas
En este proyecto se usan dos estructuras distintas:
- `int[] notas` en `Estudiante`
- `ArrayList<Curso>` en `PlanEstudios` y `Estudiante`

Explica por qué en cada caso se eligió esa estructura y no la otra. ¿Qué
pasa si el estudiante intenta registrar más notas que la capacidad del
arreglo?

> _Tu respuesta: El int[] se usa para un límite fijo y eficiente de notas; si se excede, lanza un error de desbordamiento. El ArrayList se usa porque la cantidad de cursos es dinámica y puede cambiar con libertad.