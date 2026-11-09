<div align="center">

# 🎬 INFORME DE FIN DE UNIDAD

**FEIRNNR - Carrera de Computación**

![Asignatura](https://img.shields.io/badge/Asignatura-Base%20de%20datos-1f6feb?style=for-the-badge&logo=databricks&logoColor=white)
![Ciclo](https://img.shields.io/badge/Ciclo-3%20A-8957e5?style=for-the-badge)
![Unidad](https://img.shields.io/badge/Unidad-1-2da44e?style=for-the-badge)
![MySQL](https://img.shields.io/badge/MySQL-8.4-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

</div>

---

## 👤 Datos Generales

| | |
| :--- | :--- |
| 📘 **Asignatura** | Base de datos |
| 🎓 **Ciclo** | 3 A |
| 🔢 **Unidad** | 1 |
| 🎯 **Resultado de aprendizaje de la unidad** | Modela bases de datos de problemas reales, bajo los principios de solidaridad, transparencia, responsabilidad y honestidad. |
| 👨‍🏫 **Nombre del Docente** | Edwin René Guamán Quinche |
| 📅 **Fecha** | 05/11/2026 |
| 🧑‍🎓 **Nombres y apellidos del estudiante** | Valeria Idaly Agila Gomez |

---

## 📌 1. TITULO

Diseño e implementación de una base de datos relacional para la gestión de películas, funciones, salas y venta de boletos de un cine en la ciudad de Loja (caso de estudio: Cinemas In).

---

## 📋 2. CONTEXTO DEL PROBLEMA

En la ciudad de Loja funciona Cinemas In, un cine ubicado en el centro comercial Plaza del Valle Shopping [2]. Al revisar su sitio web oficial [1], observé que solo permite consultar la cartelera y los horarios de las películas, y que no ofrece compra de boletos ni reserva de asientos en línea. Por lo tanto, la compra de entradas se realiza de manera presencial en las taquillas del establecimiento, donde cada cliente elige su asiento entre los que están disponibles al momento de la compra.

A partir de este entorno, el proyecto plantea la necesidad de organizar, mediante una base de datos relacional, la información que maneja un cine. No se dispone de información sobre los procedimientos internos que Cinemas In utiliza para administrar sus datos, por lo que no se atribuyen deficiencias al establecimiento. Como supuesto académico, se consideran las dificultades que podrían surgir si esta información se manejara en registros manuales u hojas independientes: la duplicación de los datos de una película, la asignación de un mismo asiento a más de un cliente, la programación de dos funciones en la misma sala y a la misma hora, y la dificultad para consultar la cantidad de boletos vendidos o los ingresos generados por película. Estas situaciones muestran la importancia de contar con una estructura que relacione los datos y establezca restricciones para mantener su integridad y consistencia.

Esta necesidad involucra principalmente al personal de taquilla, a la administración del cine y a los clientes. El personal de taquilla necesita registrar las ventas y consultar las funciones y los asientos disponibles; la administración requiere información organizada y confiable para realizar consultas y obtener resúmenes de las operaciones; y los clientes necesitan que los datos de su compra (función, asiento y precio pagado) queden registrados correctamente. De manera indirecta, también interesa a las personas que consultan la cartelera y los horarios del cine.

Para atender esta necesidad se requiere gestionar la siguiente información: géneros y películas (título, duración, clasificación, fecha de estreno y estado); actores y el papel que interpretan en cada película; salas (capacidad, tipo y estado); funciones (fecha, hora, precio, idioma y estado); clientes (cédula, nombres, apellidos, correo electrónico, teléfono y fecha de registro); y boletos (asiento, precio pagado, fecha de compra y método de pago). Gestionar estos datos correctamente es importante porque evita la duplicidad de información, mantiene las relaciones entre los registros, controla la asignación de asientos y facilita consultas como la cantidad de boletos vendidos y los ingresos por película.

En consecuencia, el proyecto propone diseñar e implementar una base de datos relacional para registrar, organizar y consultar la información de películas, actores, salas, funciones, clientes y boletos. Su alcance se limita a la gestión de estos datos y no incluye el desarrollo de funcionalidades de compra de entradas ni de reserva de asientos por internet.

Finalmente, se distingue el origen de la información presentada. La ubicación de Cinemas In en Plaza del Valle Shopping y la existencia de su sitio web oficial se respaldan en las fuentes citadas [1], [2]. La ausencia de compra y reserva en línea, así como la compra presencial de entradas en taquilla, corresponden a observaciones realizadas durante la revisión del sitio web. Las posibles dificultades del manejo manual de la información son supuestos planteados con fines académicos. Por último, los datos de ejemplo de este proyecto son ficticios y no representan la cartelera, los precios ni los clientes reales del establecimiento.

---

## 🎯 3. OBJETIVOS

### 🏁 3.1. Objetivo General

Diseñar e implementar una base de datos relacional en MySQL, a partir de los modelos Entidad-Relación y relacional, para organizar y gestionar la información de películas, funciones, salas, clientes y boletos de un cine de la ciudad de Loja, garantizando la integridad y la consistencia de los datos.

### 📍 3.2. Objetivos Específicos

- Elaborar el diagrama Entidad-Relación del sistema de cine, con siete entidades, sus atributos, relaciones y cardinalidades, y derivar de él el modelo relacional de ocho tablas con sus claves primarias y foráneas.

- Construir el esquema en MySQL mediante sentencias DDL y DML, con al menos cinco registros por tabla, e implementar cinco consultas formuladas en álgebra relacional y traducidas a SQL.

---

## 🧬 4. MODELOS CONCEPTUALES DE BASES DE DATOS

### 🔷 4.1. Modelo Entidad-Relación (E-R)

El diagrama Entidad-Relación se elaboró con la notación de Chen [4]. Las entidades se representan con rectángulos, las relaciones con rombos y los atributos con elipses; la clave primaria se subraya, el atributo derivado se dibuja con línea discontinua y la cardinalidad de cada relación se indica con los valores 1, N y M junto a las entidades. El modelo tiene siete entidades (GENERO, PELICULA, ACTOR, SALA, FUNCION, CLIENTE y BOLETO), que cubren la información de la cartelera, la programación de las funciones y la venta de boletos en taquilla, y seis relaciones: CLASIFICA (1:N), REPARTO (M:N), PROGRAMA (1:N), ALBERGA (1:N), TIENE (1:N) y COMPRA (1:N). Todos los atributos son simples, salvo asientos_disponibles, que es un atributo derivado.

<div align="center">

<img width="652" height="499" alt="figura1-diagrama-er" src="https://github.com/user-attachments/assets/2d2b965d-a687-42df-b1a6-be91469a8a1c" />

***Figura 1. Diagrama Entidad-Relación del sistema de gestión de un cine (caso Cinemas In, Loja).***

</div>

### 🔶 4.2. Modelo Relacional

El modelo relacional se obtuvo a partir del diagrama E-R [3]. Cada entidad se convirtió en una tabla y cada relación 1:N se resolvió colocando una clave foránea (FK) en la tabla del lado N. La relación REPARTO, de tipo M:N, se resolvió con una tabla intermedia del mismo nombre, cuya clave primaria está formada por id_pelicula e id_actor y que conserva el atributo papel. El atributo derivado asientos_disponibles no se almacena, porque puede calcularse restando, a la capacidad de la sala, los boletos vendidos de la función. En total resultan ocho tablas: siete provenientes de las entidades y una intermedia. Las claves foráneas son siete: PELICULA.id_genero → GENERO; REPARTO.id_pelicula → PELICULA; REPARTO.id_actor → ACTOR; FUNCION.id_pelicula → PELICULA; FUNCION.id_sala → SALA; BOLETO.id_funcion → FUNCION y BOLETO.id_cliente → CLIENTE.

<div align="center">

<img width="608" height="482" alt="modelo relacional 1" src="https://github.com/user-attachments/assets/5626a19a-cf66-4467-8291-506ef209177b" />

***Figura 2. Modelo relacional del sistema de cine en notación de relaciones.***

</div>

A continuación se presenta el mismo modelo en formato de tablas, elaborado con la herramienta CASE draw.io, en el que se muestran los atributos de cada tabla con su tipo de dato, las claves primarias (PK), las claves foráneas (FK) y las cardinalidades entre tablas.

<div align="center">

<img width="1006" height="505" alt="Modelo Relacional 2" src="https://github.com/user-attachments/assets/b3b73af4-c94d-4fba-accc-becf1a235f49" />

***Figura 3. Modelo relacional del sistema de cine en formato de tablas (draw.io).***

</div>

---

## 💻 CÓDIGO SQL

### 🏗️ 5.1. Creación de Tablas (DDL)

A continuación, se presenta el código SQL de creación de las tablas del modelo relacional del sistema de cine. Se emplean nombres de tabla en mayúsculas, tipos de datos apropiados y las restricciones PRIMARY KEY, FOREIGN KEY, NOT NULL, UNIQUE, DEFAULT y CHECK para garantizar la integridad y la consistencia de los datos. Las tablas se crean en el orden que exigen las claves foráneas: primero las que no dependen de otras (GENERO, ACTOR, SALA, CLIENTE) y después las que las referencian.

```sql
CREATE TABLE GENERO (
  id_genero INT NOT NULL AUTO_INCREMENT,
  nombre VARCHAR(50) NOT NULL UNIQUE,
  PRIMARY KEY (id_genero)
);

CREATE TABLE ACTOR (
  id_actor INT NOT NULL AUTO_INCREMENT,
  nombre VARCHAR(100) NOT NULL,
  nacionalidad VARCHAR(50) NOT NULL,
  PRIMARY KEY (id_actor)
);

CREATE TABLE PELICULA (
  id_pelicula INT NOT NULL AUTO_INCREMENT,
  titulo VARCHAR(150) NOT NULL,
  duracion INT NOT NULL CHECK (duracion > 0 AND duracion <= 400),
  clasificacion VARCHAR(20) NOT NULL DEFAULT 'Todo público'
    CHECK (clasificacion IN ('Todo público', '+12', '+15', '+18')),
  fecha_estreno DATE NOT NULL,
  estado VARCHAR(20) NOT NULL DEFAULT 'En cartelera'
    CHECK (estado IN ('En cartelera', 'Próximamente', 'Fuera de cartelera')),
  id_genero INT NOT NULL,
  PRIMARY KEY (id_pelicula),
  FOREIGN KEY (id_genero) REFERENCES GENERO (id_genero)
);

CREATE TABLE REPARTO (
  id_pelicula INT NOT NULL,
  id_actor INT NOT NULL,
  papel VARCHAR(80),
  PRIMARY KEY (id_pelicula, id_actor),
  FOREIGN KEY (id_pelicula) REFERENCES PELICULA (id_pelicula) ON DELETE CASCADE,
  FOREIGN KEY (id_actor) REFERENCES ACTOR (id_actor) ON DELETE CASCADE
);

CREATE TABLE SALA (
  id_sala INT NOT NULL AUTO_INCREMENT,
  nombre VARCHAR(30) NOT NULL UNIQUE,
  capacidad INT NOT NULL CHECK (capacidad > 0),
  tipo VARCHAR(20) NOT NULL DEFAULT 'Estándar'
    CHECK (tipo IN ('Estándar', '3D', 'VIP')),
  estado VARCHAR(20) NOT NULL DEFAULT 'Activa'
    CHECK (estado IN ('Activa', 'Mantenimiento')),
  PRIMARY KEY (id_sala)
);

CREATE TABLE FUNCION (
  id_funcion INT NOT NULL AUTO_INCREMENT,
  fecha DATE NOT NULL,
  hora TIME NOT NULL,
  precio DECIMAL(6,2) NOT NULL CHECK (precio > 0),
  idioma VARCHAR(15) NOT NULL DEFAULT 'Doblada'
    CHECK (idioma IN ('Doblada', 'Subtitulada')),
  estado VARCHAR(20) NOT NULL DEFAULT 'Programada'
    CHECK (estado IN ('Programada', 'En curso', 'Finalizada', 'Cancelada')),
  id_pelicula INT NOT NULL,
  id_sala INT NOT NULL,
  PRIMARY KEY (id_funcion),
  UNIQUE (id_sala, fecha, hora),
  FOREIGN KEY (id_pelicula) REFERENCES PELICULA (id_pelicula),
  FOREIGN KEY (id_sala) REFERENCES SALA (id_sala)
);

CREATE TABLE CLIENTE (
  id_cliente INT NOT NULL AUTO_INCREMENT,
  cedula VARCHAR(10) NOT NULL UNIQUE CHECK (LENGTH(cedula) = 10),
  nombre VARCHAR(60) NOT NULL,
  apellido VARCHAR(60) NOT NULL,
  email VARCHAR(100) UNIQUE,
  telefono VARCHAR(15),
  fecha_registro DATE NOT NULL DEFAULT (CURRENT_DATE),
  PRIMARY KEY (id_cliente)
);

CREATE TABLE BOLETO (
  id_boleto INT NOT NULL AUTO_INCREMENT,
  asiento VARCHAR(5) NOT NULL,
  precio_pagado DECIMAL(6,2) NOT NULL CHECK (precio_pagado > 0),
  fecha_compra DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,
  metodo_pago VARCHAR(20) NOT NULL DEFAULT 'Efectivo'
    CHECK (metodo_pago IN ('Efectivo', 'Tarjeta', 'Transferencia')),
  id_funcion INT NOT NULL,
  id_cliente INT NOT NULL,
  PRIMARY KEY (id_boleto),
  UNIQUE (id_funcion, asiento),
  FOREIGN KEY (id_funcion) REFERENCES FUNCION (id_funcion),
  FOREIGN KEY (id_cliente) REFERENCES CLIENTE (id_cliente)
);
```

### 📥 5.2. Inserción de Datos (DML)

Los datos de ejemplo son ficticios y coherentes entre sí: todas las claves foráneas corresponden a registros existentes. Cada tabla tiene al menos cinco registros (GENERO 5, ACTOR 11, PELICULA 8, REPARTO 11, SALA 5, FUNCION 12, CLIENTE 6 y BOLETO 20). Los títulos de películas son solo ejemplos y no representan la cartelera real de Cinemas In.

```sql
INSERT INTO GENERO (id_genero, nombre) VALUES
  (1, 'Acción'),
  (2, 'Animación'),
  (3, 'Comedia'),
  (4, 'Terror'),
  (5, 'Drama');

INSERT INTO ACTOR (id_actor, nombre, nacionalidad) VALUES
  (1, 'Tom Hardy', 'Británica'),
  (2, 'Charlize Theron', 'Sudafricana'),
  (3, 'Tom Cruise', 'Estadounidense'),
  (4, 'Henry Cavill', 'Británica'),
  (5, 'Anthony Gonzalez', 'Estadounidense'),
  (6, 'Mike Myers', 'Canadiense'),
  (7, 'Eddie Murphy', 'Estadounidense'),
  (8, 'Amy Poehler', 'Estadounidense'),
  (9, 'Macaulay Culkin', 'Estadounidense'),
  (10, 'Vera Farmiga', 'Estadounidense'),
  (11, 'Song Kang-ho', 'Surcoreana');

INSERT INTO PELICULA (id_pelicula, titulo, duracion, clasificacion, fecha_estreno, estado, id_genero) VALUES
  (1, 'Mad Max: Furia en el camino', 120, '+15', '2015-05-14', 'En cartelera', 1),
  (2, 'Misión Imposible: Repercusión', 147, '+12', '2018-07-25', 'En cartelera', 1),
  (3, 'Coco', 105, 'Todo público', '2017-11-22', 'En cartelera', 2),
  (4, 'Intensamente', 95, 'Todo público', '2015-06-19', 'En cartelera', 2),
  (5, 'Shrek', 90, 'Todo público', '2001-05-18', 'En cartelera', 2),
  (6, 'Mi pobre angelito', 103, 'Todo público', '1990-11-16', 'En cartelera', 3),
  (7, 'El conjuro', 112, '+15', '2013-07-19', 'En cartelera', 4),
  (8, 'Parásitos', 132, '+15', '2019-05-30', 'En cartelera', 5);

INSERT INTO REPARTO (id_pelicula, id_actor, papel) VALUES
  (1, 1, 'Max Rockatansky'),
  (1, 2, 'Furiosa'),
  (2, 3, 'Ethan Hunt'),
  (2, 4, 'August Walker'),
  (3, 5, 'Miguel (voz)'),
  (4, 8, 'Alegría (voz)'),
  (5, 6, 'Shrek (voz)'),
  (5, 7, 'Burro (voz)'),
  (6, 9, 'Kevin McCallister'),
  (7, 10, 'Lorraine Warren'),
  (8, 11, 'Kim Ki-taek');

INSERT INTO SALA (id_sala, nombre, capacidad, tipo, estado) VALUES
  (1, 'Sala 1', 120, 'Estándar', 'Activa'),
  (2, 'Sala 2', 100, 'Estándar', 'Activa'),
  (3, 'Sala 3', 80, '3D', 'Activa'),
  (4, 'Sala 4', 60, 'VIP', 'Activa'),
  (5, 'Sala 5', 90, 'Estándar', 'Activa');

INSERT INTO FUNCION (id_funcion, fecha, hora, precio, idioma, estado, id_pelicula, id_sala) VALUES
  (1, '2026-11-06', '15:00:00', 4.50, 'Doblada', 'Programada', 3, 1),
  (2, '2026-11-06', '18:00:00', 4.50, 'Doblada', 'Programada', 4, 1),
  (3, '2026-11-06', '19:30:00', 6.00, 'Subtitulada', 'Programada', 1, 3),
  (4, '2026-11-06', '20:00:00', 8.00, 'Subtitulada', 'Programada', 8, 4),
  (5, '2026-11-07', '14:00:00', 4.50, 'Doblada', 'Programada', 5, 2),
  (6, '2026-11-07', '17:00:00', 4.50, 'Doblada', 'Programada', 3, 2),
  (7, '2026-11-07', '19:00:00', 4.50, 'Subtitulada', 'Programada', 2, 5),
  (8, '2026-11-07', '21:00:00', 4.50, 'Subtitulada', 'Programada', 7, 1),
  (9, '2026-11-08', '15:30:00', 6.00, 'Doblada', 'Programada', 4, 3),
  (10, '2026-11-08', '18:00:00', 4.50, 'Doblada', 'Programada', 6, 2),
  (11, '2026-11-08', '20:30:00', 8.00, 'Subtitulada', 'Programada', 2, 4),
  (12, '2026-11-08', '16:00:00', 4.50, 'Doblada', 'Programada', 5, 5);

INSERT INTO CLIENTE (id_cliente, cedula, nombre, apellido, email, telefono, fecha_registro) VALUES
  (1, '1104567890', 'Ana', 'Torres', 'ana.torres@correo.com', '0991234567', '2026-10-05'),
  (2, '1105678901', 'Luis', 'Granda', 'luis.granda@correo.com', '0982345678', '2026-10-12'),
  (3, '1103456789', 'María', 'Jaramillo', 'maria.jaramillo@correo.com', '0973456789', '2026-10-15'),
  (4, '1106789012', 'Carlos', 'Ortega', 'carlos.ortega@correo.com', '0964567890', '2026-10-20'),
  (5, '1102345678', 'Sofía', 'Ramón', 'sofia.ramon@correo.com', '0955678901', '2026-10-28'),
  (6, '1107890123', 'Diego', 'Cueva', NULL, '0946789012', '2026-11-01');

INSERT INTO BOLETO (id_boleto, asiento, precio_pagado, fecha_compra, metodo_pago, id_funcion, id_cliente)
VALUES
  (1, 'A5', 4.50, '2026-11-01 10:15:00', 'Efectivo', 1, 1),
  (2, 'B4', 4.50, '2026-11-01 10:16:00', 'Tarjeta', 2, 1),
  (3, 'C7', 4.50, '2026-11-02 09:30:00', 'Efectivo', 5, 1),
  (4, 'D3', 4.50, '2026-11-02 09:35:00', 'Transferencia', 7, 1),
  (5, 'A1', 4.50, '2026-11-01 16:40:00', 'Efectivo', 6, 2),
  (6, 'C3', 6.00, '2026-11-02 11:05:00', 'Tarjeta', 9, 2),
  (7, 'E5', 4.50, '2026-11-03 08:20:00', 'Efectivo', 8, 2),
  (8, 'F2', 4.50, '2026-11-02 14:10:00', 'Tarjeta', 12, 3),
  (9, 'A6', 4.50, '2026-11-02 14:12:00', 'Efectivo', 1, 3),
  (10, 'B8', 4.50, '2026-11-03 09:00:00', 'Transferencia', 10, 3),
  (11, 'C5', 6.00, '2026-11-03 09:02:00', 'Tarjeta', 9, 3),
  (12, 'D4', 6.00, '2026-11-01 18:25:00', 'Efectivo', 3, 4),
  (13, 'A2', 4.50, '2026-11-02 12:00:00', 'Efectivo', 6, 4),
  (14, 'H2', 8.00, '2026-11-03 10:30:00', 'Tarjeta', 11, 4),
  (15, 'V3', 8.00, '2026-11-01 19:00:00', 'Efectivo', 4, 5),
  (16, 'B9', 4.50, '2026-11-02 17:45:00', 'Efectivo', 10, 5),
  (17, 'D2', 4.50, '2026-11-03 07:50:00', 'Tarjeta', 7, 5),
  (18, 'V5', 8.00, '2026-11-02 20:15:00', 'Transferencia', 11, 6),
  (19, 'C4', 6.00, '2026-11-03 08:05:00', 'Efectivo', 9, 6),
  (20, 'D5', 6.00, '2026-11-01 21:30:00', 'Tarjeta', 3, 6);
```

---

## 🔍 CONSULTA DE ÁLGEBRA RELACIONAL Y TRADUCIR A SQL

A continuación se presentan cinco consultas de distinto nivel de complejidad, formuladas primero en álgebra relacional y luego traducidas a SQL (MySQL). Los resultados esperados corresponden a los datos insertados en la sección 5.2. Los operadores utilizados son selección (σ), proyección (π), reunión natural (⋈), unión (∪), intersección (∩), producto cartesiano (×), diferencia (−) y división (÷); cada consulta incorpora al menos un operador distinto de las demás.

### 1️⃣ Consulta 1 — Reunión natural / JOIN (operador: ⋈)

**🎯 Descripción del objetivo de la consulta:** Reunión (⋈) de cinco relaciones, con selección (σ) y proyección (π). Mostrar, para las funciones del 2026-11-07, el cliente que compró, la película, la sala, la hora, el asiento y el precio pagado. La reunión equivale a un producto cartesiano (×) seguido de una selección por las claves foráneas. Se usan condiciones de reunión explícitas porque CLIENTE y SALA comparten el nombre de un atributo (nombre), lo que haría incorrecta una reunión natural.

**📐 Álgebra Relacional:**

```text
π CLIENTE.nombre, CLIENTE.apellido, PELICULA.titulo, SALA.nombre, FUNCION.hora, BOLETO.asiento, BOLETO.precio_pagado (
  σ FUNCION.fecha = '2026-11-07' (
    BOLETO ⋈ BOLETO.id_cliente = CLIENTE.id_cliente CLIENTE
           ⋈ BOLETO.id_funcion = FUNCION.id_funcion FUNCION
           ⋈ FUNCION.id_pelicula = PELICULA.id_pelicula PELICULA
           ⋈ FUNCION.id_sala = SALA.id_sala SALA
  )
)
```

**💾 SQL:**

```sql
SELECT c.nombre, c.apellido, p.titulo, s.nombre AS sala, f.hora, b.asiento, b.precio_pagado
FROM BOLETO b
JOIN CLIENTE c ON b.id_cliente = c.id_cliente
JOIN FUNCION f ON b.id_funcion = f.id_funcion
JOIN PELICULA p ON f.id_pelicula = p.id_pelicula
JOIN SALA s ON f.id_sala = s.id_sala
WHERE f.fecha = '2026-11-07'
ORDER BY f.hora, b.asiento;
```

**📊 Resultado esperado:** Se obtienen 6 registros, uno por cada boleto vendido para las funciones del 7 de noviembre de 2026, ordenados por hora y asiento:

| nombre | apellido | titulo | sala | hora | asiento | precio_pagado |
| --- | --- | --- | --- | --- | --- | --- |
| Ana | Torres | Shrek | Sala 2 | 14:00 | C7 | 4.50 |
| Luis | Granda | Coco | Sala 2 | 17:00 | A1 | 4.50 |
| Carlos | Ortega | Coco | Sala 2 | 17:00 | A2 | 4.50 |
| Sofía | Ramón | Misión Imposible: Repercusión | Sala 5 | 19:00 | D2 | 4.50 |
| Ana | Torres | Misión Imposible: Repercusión | Sala 5 | 19:00 | D3 | 4.50 |
| Luis | Granda | El conjuro | Sala 1 | 21:00 | E5 | 4.50 |

---

### 2️⃣ Consulta 2 — Unión (operador: ∪)

**🎯 Descripción del objetivo de la consulta:** Obtener los clientes que compraron boletos para películas del género Acción (id_genero = 1) o del género Terror (id_genero = 4). Si un cliente compró de ambos géneros o varias veces, aparece una sola vez, porque la unión elimina duplicados.

**📐 Álgebra Relacional:**

```text
V = BOLETO ⋈ FUNCION ⋈ PELICULA        (reunión natural por id_funcion e id_pelicula)
A = π id_cliente ( σ id_genero = 1 ( V ) )
B = π id_cliente ( σ id_genero = 4 ( V ) )
π id_cliente, nombre, apellido ( CLIENTE ⋈ ( A ∪ B ) )
```

**💾 SQL:**

```sql
SELECT c.id_cliente, c.nombre, c.apellido
FROM CLIENTE c
JOIN BOLETO b ON b.id_cliente = c.id_cliente
JOIN FUNCION f ON b.id_funcion = f.id_funcion
JOIN PELICULA p ON f.id_pelicula = p.id_pelicula
WHERE p.id_genero = 1
UNION
SELECT c.id_cliente, c.nombre, c.apellido
FROM CLIENTE c
JOIN BOLETO b ON b.id_cliente = c.id_cliente
JOIN FUNCION f ON b.id_funcion = f.id_funcion
JOIN PELICULA p ON f.id_pelicula = p.id_pelicula
WHERE p.id_genero = 4
ORDER BY id_cliente;
```

**📊 Resultado esperado:** Se obtienen 5 clientes: Ana Torres, Luis Granda, Carlos Ortega, Sofía Ramón y Diego Cueva. Solo María Jaramillo queda fuera, porque no compró boletos de acción ni de terror.

| id_cliente | nombre | apellido |
| --- | --- | --- |
| 1 | Ana | Torres |
| 2 | Luis | Granda |
| 4 | Carlos | Ortega |
| 5 | Sofía | Ramón |
| 6 | Diego | Cueva |

---

### 3️⃣ Consulta 3 — Intersección (operador: ∩)

**🎯 Descripción del objetivo de la consulta:** Obtener los clientes que compraron boletos para películas del género Acción (id_genero = 1) y también para películas del género Animación (id_genero = 2).

**📐 Álgebra Relacional:**

```text
V = BOLETO ⋈ FUNCION ⋈ PELICULA        (reunión natural por id_funcion e id_pelicula)
A = π id_cliente ( σ id_genero = 1 ( V ) )
B = π id_cliente ( σ id_genero = 2 ( V ) )
π id_cliente, nombre, apellido ( CLIENTE ⋈ ( A ∩ B ) )
```

Equivalencia en SQL: MySQL 8.4 dispone del operador INTERSECT [5], de modo que la intersección de los conjuntos A y B se escribe directamente entre dos consultas SELECT. Ambas consultas se ubican en una tabla derivada que se reúne con CLIENTE para mostrar el nombre y el apellido.

**💾 SQL:**

```sql
SELECT c.id_cliente, c.nombre, c.apellido
FROM CLIENTE c
JOIN (SELECT b.id_cliente
      FROM BOLETO b
      JOIN FUNCION f ON b.id_funcion = f.id_funcion
      JOIN PELICULA p ON f.id_pelicula = p.id_pelicula
      WHERE p.id_genero = 1
      INTERSECT
      SELECT b.id_cliente
      FROM BOLETO b
      JOIN FUNCION f ON b.id_funcion = f.id_funcion
      JOIN PELICULA p ON f.id_pelicula = p.id_pelicula
      WHERE p.id_genero = 2) AS ab ON ab.id_cliente = c.id_cliente
ORDER BY c.id_cliente;
```

**📊 Resultado esperado:** Se obtienen 3 clientes: Ana Torres, Carlos Ortega y Diego Cueva. Sofía Ramón compró boletos de acción pero ninguno de animación, y Luis Granda y María Jaramillo compraron boletos de animación pero ninguno de acción, por lo que los tres quedan fuera de la intersección.

| id_cliente | nombre | apellido |
| --- | --- | --- |
| 1 | Ana | Torres |
| 4 | Carlos | Ortega |
| 6 | Diego | Cueva |

---

### 4️⃣ Consulta 4 — Producto cartesiano y Diferencia (operadores: × y −)

**🎯 Descripción del objetivo de la consulta:** Encontrar las combinaciones de sala VIP y película en cartelera que todavía no tienen ninguna función programada, para saber qué películas aún no se proyectan en la sala VIP. El producto cartesiano genera todas las combinaciones posibles de sala y película, y la diferencia elimina las que ya existen en FUNCION.

**📐 Álgebra Relacional:**

```text
A = π SALA.id_sala, SALA.nombre, PELICULA.id_pelicula, PELICULA.titulo ( σ tipo = 'VIP' ( SALA ) × σ estado = 'En cartelera' ( PELICULA ) )

B = π SALA.id_sala, SALA.nombre, PELICULA.id_pelicula, PELICULA.titulo ( SALA ⋈ SALA.id_sala = FUNCION.id_sala FUNCION ⋈ FUNCION.id_pelicula = PELICULA.id_pelicula PELICULA )

A − B
```

Equivalencia en SQL: el producto cartesiano se escribe con CROSS JOIN y la diferencia con el operador EXCEPT, disponible en MySQL desde la versión 8.0.31, igual que INTERSECT [5]. Ambos SELECT devuelven las mismas columnas, como exige la diferencia.

**💾 SQL:**

```sql
SELECT s.id_sala, s.nombre AS sala, p.id_pelicula, p.titulo
FROM SALA s
CROSS JOIN PELICULA p
WHERE s.tipo = 'VIP'
  AND p.estado = 'En cartelera'
EXCEPT
SELECT s.id_sala, s.nombre, p.id_pelicula, p.titulo
FROM FUNCION f
JOIN SALA s ON f.id_sala = s.id_sala
JOIN PELICULA p ON f.id_pelicula = p.id_pelicula
ORDER BY id_pelicula;
```

**📊 Resultado esperado:** La sala VIP (Sala 4) combinada con las 8 películas da 8 combinaciones; como la Sala 4 ya tiene funciones de «Parásitos» y «Misión Imposible: Repercusión», quedan 6 registros:

| id_sala | sala | id_pelicula | titulo |
| --- | --- | --- | --- |
| 4 | Sala 4 | 1 | Mad Max: Furia en el camino |
| 4 | Sala 4 | 3 | Coco |
| 4 | Sala 4 | 4 | Intensamente |
| 4 | Sala 4 | 5 | Shrek |
| 4 | Sala 4 | 6 | Mi pobre angelito |
| 4 | Sala 4 | 7 | El conjuro |

---

### 5️⃣ Consulta 5 — División (operador: ÷)

**🎯 Descripción del objetivo de la consulta:** Obtener los clientes que han comprado boletos para todas las películas del género Animación (id_genero = 2): Coco, Intensamente y Shrek.

**📐 Álgebra Relacional:**

```text
R = π id_cliente, id_pelicula ( BOLETO ⋈ FUNCION )
S = π id_pelicula ( σ id_genero = 2 ( PELICULA ) )
π id_cliente, nombre, apellido ( CLIENTE ⋈ ( R ÷ S ) )
```

Equivalencia en SQL: MySQL no cuenta con un operador de división, por lo que se expresa mediante doble negación (NOT EXISTS): un cliente cumple la condición si no existe ninguna película de animación para la cual no tenga un boleto. La consulta externa recorre los clientes y las dos subconsultas verifican la condición «todas».

**💾 SQL:**

```sql
SELECT c.id_cliente, c.nombre, c.apellido
FROM CLIENTE c
WHERE NOT EXISTS (
      SELECT 1
      FROM PELICULA p
      WHERE p.id_genero = 2
        AND NOT EXISTS (
              SELECT 1
              FROM BOLETO b
              JOIN FUNCION f ON b.id_funcion = f.id_funcion
              WHERE b.id_cliente = c.id_cliente
                AND f.id_pelicula = p.id_pelicula))
ORDER BY c.id_cliente;
```

**📊 Resultado esperado:** Se obtienen 2 clientes: Ana Torres (vio Coco, Intensamente y Shrek) y María Jaramillo (vio Shrek, Coco e Intensamente). Los demás clientes no tienen boletos para las tres películas.

| id_cliente | nombre | apellido |
| --- | --- | --- |
| 1 | Ana | Torres |
| 3 | María | Jaramillo |

---

## ✅ CONCLUSIONES

- **Conclusión 1:** Al elaborar el diagrama E-R y el modelo relacional aprendí que el diseño debe partir de identificar únicamente las entidades que el sistema necesita; en este caso, siete que representan la cartelera, las funciones y la venta de boletos. La mayor dificultad fue decidir qué datos correspondían a cada entidad y qué relaciones eran necesarias, sobre todo la de PELICULA y ACTOR, que resultó M:N y obligó a crear la tabla intermedia REPARTO. También comprendí que las cardinalidades deben definirse con cuidado, porque de ellas depende en qué tabla se coloca cada clave foránea [3], [4].

- **Conclusión 2:** Escribir el código SQL me permitió entender cómo un diseño se convierte en una base de datos funcional. Con el DDL comprobé que las restricciones PRIMARY KEY, FOREIGN KEY, UNIQUE, CHECK y DEFAULT son las que garantizan la integridad de los datos; por ejemplo, impiden vender dos veces el mismo asiento de una función o programar dos funciones en la misma sala y a la misma hora. Con el DML verifiqué que los datos deben insertarse en el orden que exigen las claves foráneas. Los aspectos más relevantes del lenguaje fueron las restricciones de integridad y la elección de tipos de datos apropiados [3].

- **Conclusión 3:** El álgebra relacional facilitó la construcción de las consultas porque, antes de escribir el SQL, había que definir qué tablas intervienen, qué condiciones se aplican y qué columnas se muestran. Las consultas más útiles para obtener información del sistema fueron las que reúnen varias tablas y las que combinan conjuntos de clientes, como los boletos por función o los clientes que vieron acción y animación. Además, la unión, la intersección y la diferencia tienen traducción directa en MySQL mediante UNION, INTERSECT y EXCEPT, el producto cartesiano se escribe con CROSS JOIN, mientras que la división no tiene operador propio y se resolvió con doble NOT EXISTS, lo que muestra que el álgebra relacional es la base lógica del SQL [3], [5].

---

## 📚 BIBLIOGRAFÍA

[1] Cinemas In, «Cinemas In – Más cerca de las estrellas.» [En línea]. Disponible en: https://cinemasin.com.ec/. [Accedido: 5-nov-2026].

[2] Vondom, «The modern decoration of Cinemas In.» [En línea]. Disponible en: https://vondom.com/projects/cinemas-in-avantgarde-furniture/. [Accedido: 5-nov-2026].

[3] A. Silberschatz, H. F. Korth y S. Sudarshan, *Database System Concepts*, 7.ª ed. Nueva York, NY, EE. UU.: McGraw-Hill Education, 2020. ISBN: 978-0-07-802215-9.

[4] P. P.-S. Chen, «The entity-relationship model—Toward a unified view of data,» *ACM Trans. Database Syst.*, vol. 1, n.º 1, pp. 9–36, mar. 1976, doi: 10.1145/320434.320440.

[5] Oracle Corporation, «MySQL 8.4 Reference Manual: 15.2.8 INTERSECT Clause.» [En línea]. Disponible en: https://dev.mysql.com/doc/refman/8.4/en/intersect.html. [Accedido: 5-nov-2026].
