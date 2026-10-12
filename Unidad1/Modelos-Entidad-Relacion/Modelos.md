# 🧩 Modelo Entidad-Relación

## 📖 1. Introducción

El modelo entidad-relación (E-R) es una herramienta utilizada
para representar gráficamente los datos relevantes de un sistema
de información, así como las relaciones existentes entre ellos.

Este modelo permite comprender cómo se organiza la información
antes de implementar una base de datos, facilitando la identificación
de los elementos que intervienen en el sistema.

El modelo E-R representa una realidad mediante entidades,
atributos y relaciones, proporcionando una visión estructurada
de los datos que se necesitan almacenar.

## 🎯 2. Importancia del modelo entidad-relación

El modelo entidad-relación es importante porque permite:

- Comprender el mundo real que se desea representar.
- Identificar los elementos relevantes de un sistema.
- Representar gráficamente las entidades y sus relaciones.
- Organizar la información antes de implementar una base de datos.
- Facilitar la transformación del modelo E-R en un modelo relacional.

## 🏗️ 3. Proceso de modelamiento de una base de datos

Para realizar el modelamiento de una base de datos se consideran
las siguientes etapas:

1. **Comprender el mundo real:** identificar la situación o el
   sistema que se desea representar.
2. **Elaborar el modelo entidad-relación:** representar gráficamente
   las entidades, sus propiedades y las relaciones existentes.
3. **Transformar el modelo:** convertir el modelo E-R en un modelo
   relacional que facilite su implementación.

---

## 🧱 4. Elementos del modelo entidad-relación

Los principales elementos del modelo E-R son las entidades,
los atributos y las relaciones.

### 🟣 4.1. Entidad

Una entidad es un objeto o concepto del mundo real que puede
distinguirse de los demás y que resulta relevante para el sistema.

Puede representar objetos de existencia física o conceptual.

**Ejemplos:**
- Estudiante.
- Profesor.
- Libro.
- Cliente.
- Producto.

Cada entidad posee características propias que permiten
describirla e identificarla.

### 🟣 4.2. Conjunto de entidades

Un conjunto de entidades es una colección de entidades del
mismo tipo que comparten una estructura de atributos.

**Ejemplo:**

El conjunto `CLIENTES` agrupa a todos los clientes registrados
en un sistema de ventas.

### 🟣 4.3. Clasificación de las entidades

Las entidades se clasifican en fuertes y débiles.

#### Entidad fuerte

Es aquella que puede existir independientemente de otra entidad
y dispone de una clave propia que permite identificarla.

**Ejemplo:** una entidad `FACTURA` que posee su propio
identificador.

#### Entidad débil

Es aquella cuya existencia depende de otra entidad y que no puede
identificarse completamente utilizando únicamente sus propios
atributos.

**Ejemplo:** una entidad `ARTICULO_FACTURADO` que depende
de una factura para identificarse dentro del sistema.

### 🟣 4.4. Atributos

Los atributos son las propiedades o características que describen
a una entidad.

**Ejemplo:**

La entidad `ESTUDIANTE` puede tener los siguientes atributos:

- id_estudiante
- nombre
- apellido
- fecha_nacimiento
- correo

#### Tipos de atributos

**Atributo atómico:** no puede dividirse en componentes más pequeños
dentro del modelo.

Ejemplo: número de cédula.

**Atributo compuesto:** puede dividirse en subpartes.

Ejemplo: dirección, que puede incluir calle principal,
calle secundaria y número de casa.

**Atributo monovalor:** tiene un único valor para cada entidad.

Ejemplo: fecha de nacimiento.

**Atributo multivalor:** puede tener varios valores para una entidad.

Ejemplo: los números de teléfono de una persona.

**Atributo derivado:** su valor se obtiene a partir de otros atributos.

Ejemplo: la edad, que puede calcularse utilizando la fecha
de nacimiento.

**Atributo clave:** permite identificar de manera única
una entidad.

Ejemplo: id_estudiante.

**Atributo nulo:** representa la ausencia de un valor para
un atributo determinado.

### 🟣 4.5. Claves

Las claves permiten identificar entidades y distinguirlas
de las demás.

- **Superclave:** conjunto de uno o más atributos cuyos valores
  permiten identificar de forma única una entidad.
- **Clave candidata:** superclave mínima, es decir, no contiene
  atributos innecesarios para cumplir esa función.
- **Clave primaria:** clave candidata seleccionada para identificar
  de manera única cada entidad.

### 🟣 4.6. Relaciones

Una relación representa una asociación entre entidades de un mismo
conjunto o de conjuntos diferentes.

**Ejemplo:**

Un estudiante se matricula en una asignatura.

En este caso, `ESTUDIANTE` y `ASIGNATURA` son entidades,
mientras que `SE_MATRICULA` representa la relación entre ellas.

Las relaciones pueden involucrar dos o más conjuntos de entidades.

Según su grado, pueden ser:

- **Binarias:** participan dos conjuntos de entidades.
- **Ternarias:** participan tres conjuntos de entidades.

También pueden distinguirse:

- **Relaciones identificadoras:** vinculan una entidad débil
  con su entidad propietaria.
- **Relaciones descriptoras:** representan una asociación entre
  entidades sin transferir atributos identificadores entre ellas.

---

## 🔗 5. Cardinalidad de las relaciones

La cardinalidad indica cuántas entidades de un conjunto pueden
relacionarse con entidades de otro conjunto.

### 5.1. Relación uno a uno (1:1)

Una entidad de un conjunto se relaciona con una entidad
de otro conjunto, y viceversa.

**Ejemplo:**

Un departamento tiene un único director y cada director
dirige como máximo un departamento.

### 5.2. Relación uno a muchos (1:N)

Una entidad puede relacionarse con varias entidades de otro conjunto,
pero cada una de estas últimas se relaciona con una sola entidad
del primer conjunto.

**Ejemplo:**

Un departamento puede tener varios profesores, mientras que
cada profesor pertenece a un solo departamento.

### 5.3. Relación muchos a uno (N:1)

Varias entidades de un conjunto pueden relacionarse con una
misma entidad del otro conjunto.

**Ejemplo:**

Varios profesores pueden pertenecer al mismo departamento.

### 5.4. Relación muchos a muchos (N:M)

Varias entidades de un conjunto pueden relacionarse con varias
entidades del otro conjunto.

**Ejemplo:**

Un profesor puede impartir varias asignaturas y una asignatura
puede ser impartida por varios profesores.

En el diseño relacional, esta relación puede transformarse
mediante la incorporación de una entidad intermedia que permita
representar las asociaciones entre ambas entidades.

---

## 🎨 6. Simbología del modelo entidad-relación

En la representación gráfica tradicional del modelo E-R
se utilizan los siguientes símbolos:

| Elemento | Representación |
|---|---|
| Entidad | Rectángulo |
| Atributo | Elipse |
| Relación | Rombo |
| Atributo multivalor | Elipse doble |
| Atributo derivado | Elipse discontinua |
| Clave primaria | Atributo subrayado |
| Conexiones entre elementos | Líneas |

Estos símbolos permiten representar gráficamente los componentes
del modelo y comprender cómo se relacionan entre sí.

---

## 📝 7. Diseño de diagramas entidad-relación

Para elaborar un diagrama E-R se deben considerar las siguientes
actividades:

1. Seleccionar los conjuntos de entidades.
2. Identificar las propiedades o atributos de cada entidad.
3. Determinar las relaciones entre las entidades.
4. Definir las cardinalidades de las relaciones.
5. Describir las propiedades de las relaciones, cuando corresponda.
6. Revisar que el diseño represente adecuadamente la situación real.

El diseño de un modelo E-R puede variar según las decisiones
tomadas durante el análisis. Estas decisiones influyen en la
facilidad de implementación, el rendimiento y la posibilidad
de modificar o ampliar el modelo posteriormente.

---

## 📌 8. Conclusión

El modelo entidad-relación constituye una herramienta fundamental
para el análisis y diseño de bases de datos.

Mediante la identificación de entidades, atributos, claves,
relaciones y cardinalidades, permite representar los elementos
relevantes de un sistema antes de su implementación.

Su elaboración facilita la comprensión de los datos y sirve
como base para transformar el diseño conceptual en un modelo
relacional.

---

## ✏️ 9. Ejercicios prácticos

En esta sección se incorporarán los ejercicios realizados
durante las clases sobre modelos entidad-relación.

- [📝 Ejercicio 1](Ejercicio01.md)
- [📝 Ejercicio 2](Ejercicio02.md)
- [📝 Ejercicio 3](Ejercicio03.md)

---

⬅️ [Volver a la Unidad 1](../Unidad1.md)
