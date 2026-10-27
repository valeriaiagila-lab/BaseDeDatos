# 🩺 Ejercicio 3: Clínica Médica

**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 1. Análisis del problema
Los pacientes solicitan citas; cada cita la atiende un médico a un paciente en fecha, hora y consultorio. De algunas citas se genera una receta que incluye medicamentos con dosis y duración. Cada médico pertenece a una especialidad.



## 2. Diagrama Entidad-Relación

El diagrama representa las entidades principales de la clínica, sus relaciones y las cardinalidades correspondientes.

<img width="962" height="444" alt="Clinica" src="https://github.com/user-attachments/assets/05561ced-bbd3-453d-89ef-1ea983e92a6d" />

---

## 3. Modelo Relacional
<img width="443" height="484" alt="Modelo Relacional Clinica" src="https://github.com/user-attachments/assets/4cb978cc-98c9-405a-87dc-25d105acd24d" />


---

## 🖼️ 4. Codigo MySQL
```sql

Create Table Especialidad (
    id_especialidad Int Primary Key,
    nombre          Varchar(80) Not Null
);
 
Create Table Medico (
    id_medico       Int Primary Key,
    nombre          Varchar(100) Not Null,
    id_especialidad Int Not Null,
    Foreign Key (id_especialidad) References Especialidad (id_especialidad)
);
 
Create Table Paciente (
    id_paciente Int Primary Key,
    nombre      Varchar(100) Not Null
);
 
Create Table Cita (
    id_cita     Int Primary Key,
    fecha       Date Not Null,
    hora        Time Not Null,
    consultorio Varchar(20) Not Null,
    id_paciente Int Not Null,
    id_medico   Int Not Null,
    Foreign Key (id_paciente) References Paciente (id_paciente),
    Foreign Key (id_medico)   References Medico (id_medico)
);
 
Create Table Receta (
    id_receta Int Primary Key,
    dosis     Varchar(100) Not Null,
    duracion  Varchar(50)  Not Null,
    id_cita   Int Not Null Unique,
    Foreign Key (id_cita) References Cita (id_cita)
);
 
Create Table Medicamento (
    id_medicamento Int Primary Key,
    nombre         Varchar(100) Not Null
);
 
Create Table Incluye (
    id_receta      Int Not Null,
    id_medicamento Int Not Null,
    Primary Key (id_receta, id_medicamento),
    Foreign Key (id_receta)      References Receta (id_receta),
    Foreign Key (id_medicamento) References Medicamento (id_medicamento)
);



```

---
## 🖼️ 5. Base de datos creada
----

<img width="232" height="223" alt="ejer2" src="https://github.com/user-attachments/assets/56ea7a9d-1f3f-44d4-825d-8b64af915842" />

---


[⬅️ Volver al índice de modelos](Modelos.md)
