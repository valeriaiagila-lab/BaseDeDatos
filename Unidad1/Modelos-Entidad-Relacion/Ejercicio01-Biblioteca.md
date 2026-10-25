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


Create Table Autor (
    id_autor Int Primary Key,
    nombre   Varchar(100) Not Null
);

Create Table Libro (
    id_libro Int Primary Key,
    titulo   Varchar(150) Not Null
);

Create Table Escrito (
    id_libro Int Not Null,
    id_autor Int Not Null,
    Primary Key (id_libro, id_autor),
    Foreign Key (id_libro) References Libro (id_libro),
    Foreign Key (id_autor) References Autor (id_autor)
);

Create Table Socio (
    id_socio Int Primary Key,
    nombre   Varchar(100) Not Null
);

Create Table Prestamo (
    id_libro         Int  Not Null,
    id_socio         Int  Not Null,
    fecha_retiro     Date Not Null,
    fecha_devolucion Date,
    Primary Key (id_libro, id_socio),
    Foreign Key (id_libro) References Libro (id_libro),
    Foreign Key (id_socio) References Socio (id_socio)
);

```

---


[⬅️ Volver al índice de modelos](Modelos.md)


