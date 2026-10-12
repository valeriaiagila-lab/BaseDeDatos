# 📚 Ejercicio 1: Sistema de Biblioteca 📖

**📘 Asignatura:** Base de Datos  
**🧩 Tema:** Modelo Entidad-Relación

---

## 🔎 1. Análisis del problema

🏛️ Una biblioteca necesita organizar la información de sus libros, autores, socios y préstamos. El sistema debe permitir conocer qué autores están relacionados con cada libro y registrar los préstamos realizados por los socios.

📅 Además, cada préstamo debe conservar la fecha de retiro y la fecha de devolución del libro.

---

## 🏷️ 2. Identificación de entidades y atributos

### 📕 Libro

Representa los libros registrados en la biblioteca. 📚

### ✍️ Autor

Representa a las personas que escriben los libros. 🖊️

### 🧑‍🎓 Socio

Representa a las personas que solicitan préstamos. 🤝

### 🔄 Préstamo

Permite registrar el préstamo realizado por un socio. 📖

**📌 Atributos:**
- 🗓️ Fecha de retiro.
- 📅 Fecha de devolución.

---

## 🔗 3. Relaciones y cardinalidades

### 📚 Libro - Autor

Un libro puede tener varios autores y un autor puede escribir varios libros. ✍️

**🔢 Cardinalidad:** Muchos a muchos (N:M).

### 🧑‍🎓 Socio - Préstamo

Un socio puede realizar varios préstamos y cada préstamo corresponde a un socio. 🔄

**🔢 Cardinalidad máxima:** Uno a muchos (1:N).

### 📕 Libro - Préstamo

La relación permite identificar los libros que se prestan y registrar las fechas correspondientes a cada préstamo. 📅

---

## 🖼️ 4. Diagrama Entidad-Relación

<img width="588" height="292" alt="bibliotec" src="https://github.com/user-attachments/assets/7bde993e-b63c-413e-bb5c-82e5b6e82623" />
---

## 🎯 5. Conclusión

✅ El modelo entidad-relación permite organizar la información de los libros, autores, socios y préstamos de una biblioteca. También facilita el registro de las fechas de retiro y devolución y representa la relación entre los libros y sus autores. 📚

---

⬅️ [📑 Volver al índice de modelos](Modelos.md)


