## 🎓 Ejercicio 11: Universidad

------
**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 🔎 1. Análisis del problema

La universidad necesita organizar la información de los alumnos y los cursos en los que se inscriben.

Las inscripciones registran el ciclo y la calificación obtenida. Además, algunos cursos requieren haber aprobado otros cursos previamente y pueden establecer una nota mínima como prerrequisito.

## 🏷️ 2. Identificación de entidades y atributos

| Entidad | Descripción |
|---|---|
| Alumno | Representa a los estudiantes de la universidad. |
| Curso | Representa los cursos ofrecidos. |

### 📋 Atributos identificados

- **Alumno:** identificador y nombre.
- **Curso:** identificador y nombre.
- **Inscripción:** ciclo y calificación.
- **Prerrequisitos:** nota mínima.

## 🔗 3. Relaciones y cardinalidades

| Relación | Descripción | Cardinalidad según el diagrama |
|---|---|---|
| Alumno - Curso | Los alumnos se inscriben en cursos. | N:M |
| Curso - Curso | Representa los prerrequisitos entre cursos. | N:M |

### 📝 Análisis de las relaciones

- **Alumno - Curso:** La relación `Inscribe` registra el ciclo y la calificación obtenida por el alumno.
- **Curso - Curso:** La relación recursiva `Prerrequisitos` representa los cursos que deben aprobarse antes de cursar otros y permite registrar la nota mínima.

## 🗺️ 4. Diagrama Entidad-Relación

<img width="659" height="243" alt="universidad" src="https://github.com/user-attachments/assets/9cb00681-a227-4d0f-b1ae-ca54d10d0440" />

## ✅ 5. Conclusión

El modelo permite organizar los alumnos, cursos e inscripciones, registrando las calificaciones obtenidas por ciclo. También representa los prerrequisitos y las notas mínimas exigidas para acceder a determinados cursos.

---

[⬅️ Volver al índice de modelos](Modelos.md)
