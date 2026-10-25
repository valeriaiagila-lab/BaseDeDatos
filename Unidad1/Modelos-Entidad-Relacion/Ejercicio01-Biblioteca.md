# 📚 Ejercicio 1: Sistema de Biblioteca

**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 🔎 1. Enunciado

Una biblioteca registra libros y autores. Un libro puede tener varios autores y un autor varios libros. Los socios toman libros prestados; de cada préstamo interesan la fecha de retiro y la de devolución.


## 🖼️ 2. Diagrama Entidad-Relación

El siguiente diagrama representa las entidades principales y sus relaciones.




<img width="971" height="364" alt="Biblioteca" src="https://github.com/user-attachments/assets/ce0eed71-8026-41eb-878b-28d5612d846f" />


---
## 🖼️ 3.Modelo Relacional
<img width="447" height="396" alt="Modelo Relacional biblioteca" src="https://github.com/user-attachments/assets/e506106c-6e43-40b6-879b-1f0d74e393a2" />


---


## 🖼️ 4. Codigo MySQL
```sql
CREATE DATABASE ej1_biblioteca;
USE ej1_biblioteca;

CREATE TABLE Autor (
    id_autor INT PRIMARY KEY,
    nombre   VARCHAR(100) NOT NULL
);

CREATE TABLE Libro (
    id_libro INT PRIMARY KEY,
    titulo   VARCHAR(150) NOT NULL
);

CREATE TABLE Escrito (
    id_libro INT NOT NULL,
    id_autor INT NOT NULL,
    PRIMARY KEY (id_libro, id_autor),
    FOREIGN KEY (id_libro) REFERENCES Libro (id_libro),
    FOREIGN KEY (id_autor) REFERENCES Autor (id_autor)
);

CREATE TABLE Socio (
    id_socio INT PRIMARY KEY,
    nombre   VARCHAR(100) NOT NULL
);

CREATE TABLE Prestamo (
    id_libro         INT  NOT NULL,
    id_socio         INT  NOT NULL,
    fecha_retiro     DATE NOT NULL,
    fecha_devolucion DATE,
    PRIMARY KEY (id_libro, id_socio),
    FOREIGN KEY (id_libro) REFERENCES Libro (id_libro),
    FOREIGN KEY (id_socio) REFERENCES Socio (id_socio)
);
```

---


[⬅️ Volver al índice de modelos](Modelos.md)


