## 🐾 Ejercicio 9: Veterinaria

----
# 🐾 Ejemplo 9: Veterinaria

**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 🔎 1. Enunciado

- Del propietario interesa: cédula, apellidos, nombres, dirección, teléfonos.
- De la mascota interesa: identificador, nombre, fecha de nacimiento, tipo.
- Un propietario puede llevar una o varias mascotas.
- Una mascota la lleva uno y solo un propietario.
- Del personal de la clínica veterinaria interesa un código, la cédula y el nombre.
- Entre el personal de la clínica se distingue a los veterinarios y los auxiliares, pudiendo haber otros tipos.
  - Del veterinario se guarda además su fecha_alta y especialidad.
  - De los auxiliares interesa su base de cotización.
- Las mascotas pasan consulta con los veterinarios. De manera que:
  - Un veterinario puede pasar consulta a ninguna o a varias mascotas.
  - Una misma mascota de la clínica ha pasado consulta una o más veces, en fechas diferentes, con varios veterinarios.
  - Al pasar consulta se realiza un diagnóstico.
- Cada propietario tiene un familiar de contacto para casos de emergencia.
  - De este familiar interesa la cédula, nombre y teléfono.
  - Si el propietario se da de alta en la clínica veterinaria, el familiar ya no interesa.
  - El familiar es contacto de un solo propietario.


## 🗺️ 2. Diagrama Entidad-Relación


<img width="820" height="521" alt="VETERINARIA1" src="https://github.com/user-attachments/assets/1c939069-a2eb-4d64-9296-5c95c702b65f" />



---


## 🗺️ 3. Modelo Relacional
<img width="471" height="507" alt="Modelo Relacional Veterinaria " src="https://github.com/user-attachments/assets/58a47b74-df0e-4180-953e-a9403c2ec63b" />

---


## 🖼️ 4. Codigo MySQL
```sql
CREATE DATABASE ej9_veterinaria;
USE ej9_veterinaria;

CREATE TABLE Propietario (
    cedula    VARCHAR(10) PRIMARY KEY,
    apellidos VARCHAR(80) NOT NULL,
    nombres   VARCHAR(80) NOT NULL,
    direccion VARCHAR(150)
);

CREATE TABLE Telefono_propietario (
    cedula   VARCHAR(10) NOT NULL,
    telefono VARCHAR(15) NOT NULL,
    PRIMARY KEY (cedula, telefono),
    FOREIGN KEY (cedula) REFERENCES Propietario (cedula)
);

CREATE TABLE Familiar_contacto (
    cedula_propietario VARCHAR(10) NOT NULL,
    cedula             VARCHAR(10) NOT NULL,
    nombre             VARCHAR(100) NOT NULL,
    telefono           VARCHAR(15),
    PRIMARY KEY (cedula_propietario, cedula),
    FOREIGN KEY (cedula_propietario) REFERENCES Propietario (cedula)
);

CREATE TABLE Mascota (
    id_mascota         INT PRIMARY KEY,
    nombre             VARCHAR(60) NOT NULL,
    fecha_nacimiento   DATE,
    tipo               VARCHAR(40) NOT NULL,
    cedula_propietario VARCHAR(10) NOT NULL,
    FOREIGN KEY (cedula_propietario) REFERENCES Propietario (cedula)
);

CREATE TABLE Personal (
    codigo INT PRIMARY KEY,
    cedula VARCHAR(10) NOT NULL UNIQUE,
    nombre VARCHAR(100) NOT NULL
);

CREATE TABLE Veterinario (
    codigo       INT PRIMARY KEY,
    fecha_alta   DATE NOT NULL,
    especialidad VARCHAR(80),
    FOREIGN KEY (codigo) REFERENCES Personal (codigo)
);

CREATE TABLE Auxiliar (
    codigo          INT PRIMARY KEY,
    base_cotizacion DECIMAL(8,2) NOT NULL,
    FOREIGN KEY (codigo) REFERENCES Personal (codigo)
);

CREATE TABLE Consulta (
    id_mascota         INT NOT NULL,
    codigo_veterinario INT NOT NULL,
    fecha              DATE NOT NULL,
    diagnostico        VARCHAR(255),
    PRIMARY KEY (id_mascota, codigo_veterinario),
    FOREIGN KEY (id_mascota)         REFERENCES Mascota (id_mascota),
    FOREIGN KEY (codigo_veterinario) REFERENCES Veterinario (codigo)
);

```

---


[⬅️ Volver al índice de modelos](Modelos.md)
