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

---
## 🖼️ 4. Codigo MySQL
```sql
CREATE DATABASE ej3_clinica;
USE ej3_clinica;

CREATE TABLE Especialidad (
    id_especialidad INT PRIMARY KEY,
    nombre          VARCHAR(80) NOT NULL
);

CREATE TABLE Medico (
    id_medico       INT PRIMARY KEY,
    nombre          VARCHAR(100) NOT NULL,
    id_especialidad INT NOT NULL,
    FOREIGN KEY (id_especialidad) REFERENCES Especialidad (id_especialidad)
);

CREATE TABLE Paciente (
    id_paciente INT PRIMARY KEY,
    nombre      VARCHAR(100) NOT NULL
);

CREATE TABLE Cita (
    id_cita     INT PRIMARY KEY,
    fecha       DATE NOT NULL,
    hora        TIME NOT NULL,
    consultorio VARCHAR(20) NOT NULL,
    id_paciente INT NOT NULL,
    id_medico   INT NOT NULL,
    FOREIGN KEY (id_paciente) REFERENCES Paciente (id_paciente),
    FOREIGN KEY (id_medico)   REFERENCES Medico (id_medico)
);

CREATE TABLE Receta (
    id_receta INT PRIMARY KEY,
    dosis     VARCHAR(100) NOT NULL,
    duracion  VARCHAR(50)  NOT NULL,
    id_cita   INT NOT NULL UNIQUE,
    FOREIGN KEY (id_cita) REFERENCES Cita (id_cita)
);

CREATE TABLE Medicamento (
    id_medicamento INT PRIMARY KEY,
    nombre         VARCHAR(100) NOT NULL
);

CREATE TABLE Incluye (
    id_receta      INT NOT NULL,
    id_medicamento INT NOT NULL,
    PRIMARY KEY (id_receta, id_medicamento),
    FOREIGN KEY (id_receta)      REFERENCES Receta (id_receta),
    FOREIGN KEY (id_medicamento) REFERENCES Medicamento (id_medicamento)
);

```

---


[⬅️ Volver al índice de modelos](Modelos.md)
