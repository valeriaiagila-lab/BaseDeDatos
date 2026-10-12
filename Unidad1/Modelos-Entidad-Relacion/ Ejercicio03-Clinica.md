# 🩺 Ejercicio 3: Clínica Médica

**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 1. Análisis del problema

La clínica necesita organizar la información de sus pacientes, médicos, citas, especialidades, recetas y medicamentos.

Cada cita debe registrar la fecha, hora y consultorio en el que se atiende al paciente. Algunas citas generan recetas que incluyen medicamentos, dosis y duración del tratamiento.

## 2. Identificación de entidades y atributos

Las entidades identificadas en el sistema son las siguientes:

| Entidad | Descripción |
|---|---|---|
| Paciente | Representa a las personas que solicitan atención médica. | 
| Médico | Representa a los profesionales que atienden las citas. | 
| Especialidad | Representa el área médica a la que pertenece cada médico. |
| Cita | Registra la atención médica programada. | 
| Receta | Representa las recetas generadas durante algunas citas. | 
| Medicamento | Representa los medicamentos incluidos en las recetas. | 
| Detalle de receta | Permite registrar los medicamentos y las indicaciones de cada tratamiento. | Dosis, duración. |

## 3. Relaciones y cardinalidades

| Relación | Descripción | Cardinalidad |
|---|---|---|
| Paciente - Cita | Un paciente puede solicitar varias citas y cada cita corresponde a un paciente. | Uno a muchos (1:N). |
| Médico - Cita | Un médico puede atender varias citas y cada cita es atendida por un médico. | Uno a muchos (1:N). |
| Especialidad - Médico | Una especialidad puede estar relacionada con varios médicos y cada médico pertenece a una especialidad. | Uno a muchos (1:N). |
| Cita - Receta | Una cita puede generar una receta y cada receta corresponde a una cita. | Uno a uno (1:0..1), si se permite una sola receta por cita. |
| Receta - Medicamento | Una receta puede incluir varios medicamentos y un medicamento puede aparecer en diferentes recetas. | Muchos a muchos (N:M). |

### Análisis de las relaciones

- **Paciente - Cita:** Un paciente puede acudir a diferentes citas médicas, pero cada cita corresponde a un único paciente.
- **Médico - Cita:** Un médico puede atender varias citas, mientras que cada cita es atendida por un médico.
- **Especialidad - Médico:** Una especialidad puede agrupar a varios médicos y cada médico pertenece a una especialidad.
- **Cita - Receta:** Algunas citas generan recetas médicas. La relación puede ser de uno a uno si cada cita genera como máximo una receta; si puede generar varias, será de uno a muchos (1:0..1).
- **Receta - Medicamento:** Es una relación de muchos a muchos, porque una receta puede incluir varios medicamentos y un medicamento puede aparecer en distintas recetas. Se representa mediante la entidad intermedia `Detalle_Receta`, que almacena la dosis y la duración del tratamiento.

## 4. Diagrama Entidad-Relación

El diagrama representa las entidades principales de la clínica, sus relaciones y las cardinalidades correspondientes.

<img width="892" height="466" alt="CITAS" src="https://github.com/user-attachments/assets/5ea067ef-5f38-44f9-90a6-882cfa7daa89" />

## 5. Conclusión

El modelo entidad-relación permite organizar la información de los pacientes, médicos, citas y recetas de una clínica. También facilita la administración de las especialidades médicas y de los medicamentos prescritos.

Además, la entidad `Detalle_Receta` permite registrar la dosis y duración de cada medicamento dentro de una receta, manteniendo organizadas las indicaciones de los tratamientos médicos.

---

[⬅️ Volver al índice de modelos](Modelos.md)
