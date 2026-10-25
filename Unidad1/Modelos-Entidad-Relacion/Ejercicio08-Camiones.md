## 🚚 Ejercicio 8: Camiones
**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 🔎 1. Enunciado

Se desea informatizar la gestión de una empresa de transporte que reparte paquetes por toda España. Los encargados de llevar los paquetes son los camioneros, de los que se quiere guardar la cédula, nombre, teléfono, dirección, salario y población en que vive. De los paquetes transportados interesa conocer el código del paquete, descripción, destinatario y dirección del destinatario.
Un camionero distribuye muchos paquetes, y un paquete sólo puede ser distribuido por un camionero. De las provincias a las que llegan los paquetes interesa guardar el código de provincia y el nombre. Un paquete sólo puede llegar a una provincia. Sin embargo, a una provincia pueden llegar varios paquetes.
De los camiones que llevan los camioneros, interesa conocer la matrícula, modelo, tipo y potencia. Un camionero puede conducir diferentes camiones en fechas diferentes, y un camión puede ser conducido por varios camioneros.

## 🗺️ 2. Diagrama Entidad-Relación

<img width="912" height="536" alt="Camion1" src="https://github.com/user-attachments/assets/c84ab62c-ed18-45c0-872f-50acc6e97953" />

---

## 🗺️ 3. Modelo Relacional


<img width="711" height="365" alt="Modelo Relacional Camiones" src="https://github.com/user-attachments/assets/4addf03e-ec64-42b7-919a-758f16277d7b" />

---


## 🖼️ 4. Codigo MySQL
```sql

CREATE DATABASE ej8_camiones;
USE ej8_camiones;

CREATE TABLE Provincia (
    codigo VARCHAR(5) PRIMARY KEY,
    nombre VARCHAR(60) NOT NULL
);

CREATE TABLE Camionero (
    cedula    VARCHAR(10) PRIMARY KEY,
    nombre    VARCHAR(100) NOT NULL,
    telefono  VARCHAR(15),
    direccion VARCHAR(150),
    salario   DECIMAL(8,2) NOT NULL,
    poblacion VARCHAR(60)
);

CREATE TABLE Paquete (
    codigo                 VARCHAR(15) PRIMARY KEY,
    descripcion            VARCHAR(200),
    destinatario           VARCHAR(100) NOT NULL,
    direccion_destinatario VARCHAR(150) NOT NULL,
    codigo_provincia       VARCHAR(5)   NOT NULL,
    cedula_camionero       VARCHAR(10)  NOT NULL,
    FOREIGN KEY (codigo_provincia) REFERENCES Provincia (codigo),
    FOREIGN KEY (cedula_camionero) REFERENCES Camionero (cedula)
);

CREATE TABLE Camion (
    matricula VARCHAR(10) PRIMARY KEY,
    modelo    VARCHAR(50),
    tipo      VARCHAR(40),
    potencia  INT
);

CREATE TABLE Conduce (
    cedula    VARCHAR(10) NOT NULL,
    matricula VARCHAR(10) NOT NULL,
    fecha     DATE NOT NULL,
    PRIMARY KEY (cedula, matricula),
    FOREIGN KEY (cedula)    REFERENCES Camionero (cedula),
    FOREIGN KEY (matricula) REFERENCES Camion (matricula)
);
```

---


[⬅️ Volver al índice de modelos](Modelos.md)
