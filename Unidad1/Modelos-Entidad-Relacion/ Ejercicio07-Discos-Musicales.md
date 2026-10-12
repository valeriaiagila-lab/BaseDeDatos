## 🎵 Ejercicio 7: Discos Musicales

----
**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 🔎 1. Análisis del problema

La tienda necesita organizar los discos musicales, sus géneros, cantantes y canciones.

Cada disco tiene un título, precio y género musical, y pertenece a un cantante. Los discos contienen canciones y se necesita conocer la posición de cada canción dentro de un disco.

## 🏷️ 2. Identificación de entidades y atributos

| Entidad | Descripción |
|---|---|
| Género | Representa los géneros musicales. |
| Disco | Representa los discos disponibles. |
| Cantante | Representa a los cantantes. |
| Canción | Representa las canciones incluidas en los discos. |

### 📋 Atributos identificados

- **Género:** identificador.
- **Disco:** identificador, precio y título.
- **Cantante:** identificador, nombre y país.
- **Canción:** identificador y título.
- **Relación Contiene:** posición de la canción en el disco.

## 🔗 3. Relaciones y cardinalidades

| Relación | Descripción | Cardinalidad según el diagrama |
|---|---|---|
| Género - Disco | Clasifica los discos por género. | 1:N |
| Disco - Cantante | Relaciona los discos con sus cantantes. | 1:N |
| Disco - Canción | Relaciona los discos con las canciones. | N:M |

### 📝 Análisis de las relaciones

- **Género - Disco:** La relación `Clasifica` conecta los discos con los géneros musicales.
- **Disco - Cantante:** La relación `Pertenece` conecta los discos con los cantantes.
- **Disco - Canción:** La relación `Contiene` conecta los discos con las canciones y registra la posición de cada canción.

## 🗺️ 4. Diagrama Entidad-Relación

![Diagrama original de Discos Musicales](diagramas_originales/07_discos_musicales.png)

## ✅ 5. Conclusión

El modelo permite organizar los discos musicales, sus géneros, cantantes y canciones, conservando la posición de las canciones dentro de cada disco.

---

[⬅️ Volver al índice de modelos](Modelos.md)
