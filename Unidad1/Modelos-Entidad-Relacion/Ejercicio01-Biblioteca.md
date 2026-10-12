# 📚 Ejercicio 1: Sistema de Biblioteca

**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 🔎 1. Análisis del problema

Una biblioteca necesita organizar la información de sus libros, autores, socios y préstamos. El sistema debe permitir conocer qué autores están relacionados con cada libro y registrar los préstamos realizados por los socios.

Además, cada préstamo debe conservar la fecha de retiro y la fecha de devolución del libro.

## 2. Identificación de entidades y atributos

Las entidades identificadas a partir del enunciado son las siguientes:

| Entidad | Descripción | Atributos |
|---|---|---|
| 📖 Libro | Representa los libros registrados en la biblioteca. | No especificados en el enunciado. |
| Autor | Representa a las personas que escriben los libros. | No especificados en el enunciado. |
| Socio | Representa a las personas que solicitan préstamos. | No especificados en el enunciado. |
| Préstamo | Representa los préstamos realizados por los socios. | Fecha de retiro, fecha de devolución. |

## 🔗 3. Relaciones y cardinalidades

| Relación | Descripción | Cardinalidad |
|---|---|---|
| Libro - Autor | Un libro puede tener varios autores y un autor puede escribir varios libros. | Muchos a muchos (N:M). |
| Socio - Préstamo | Un socio puede realizar varios préstamos y cada préstamo corresponde a un socio. | Uno a muchos (1:N). |
| Libro - Préstamo | Permite identificar los libros asociados a los préstamos realizados. | Depende de las reglas de la biblioteca. |

### Análisis de las relaciones

- **Libro - Autor:** Es una relación de muchos a muchos, ya que un libro puede tener varios autores y un autor puede escribir varios libros.
- **Socio - Préstamo:** Es una relación de uno a muchos, porque un socio puede realizar diferentes préstamos y cada préstamo corresponde a un único socio.
- **Libro - Préstamo:** Se debe determinar si cada préstamo corresponde a un solo libro o si puede incluir varios libros para establecer su cardinalidad.

## 🖼️ 4. Diagrama Entidad-Relación

El siguiente diagrama representa las entidades principales y sus relaciones.


<img width="588" height="292" alt="bibliotec" src="https://github.com/user-attachments/assets/7bde993e-b63c-413e-bb5c-82e5b6e82623" />
## 5. Conclusión

El modelo entidad-relación permite estructurar la información de una biblioteca mediante las entidades Libro, Autor, Socio y Préstamo. Las relaciones definidas representan la participación de los autores en los libros y la gestión de los préstamos realizados por los socios.

Asimismo, los atributos fecha de retiro y fecha de devolución permiten conservar información relevante sobre cada préstamo, facilitando la organización y posterior implementación de la base de datos.

---

[⬅️ Volver al índice de modelos](Modelos.md)


