## 💻 Ejercicio 6: Tienda Informática

----
**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 🔎 1. Enunciado

Se desea crear una aplicación para la gestión de una tienda informática. La tienda dispone de una serie de productos que se venden a los clientes. De cada producto informático se desea guardar el código, descripción, precio y número de existencias. De cada cliente se desea guardar el código, nombre, apellidos, dirección y número telefónico. Un cliente puede comprar varios productos en la tienda y un mismo producto puede ser comprado por varios clientes. Cada vez que se compre un artículo quedará registrada la compra en la base de datos junto con la fecha en la que se compró el artículo. La tienda tiene contactos con varios proveedores que son los que suministran los productos. Un mismo producto puede ser suministrado por varios proveedores. De cada proveedor se desea guardar el código, nombres, apellidos, dirección, provincia y número de teléfono.

## 🗺️ 2. Diagrama Entidad-Relación

<img width="622" height="180" alt="Tienda" src="https://github.com/user-attachments/assets/ea69d7c1-cbbd-4b73-9eae-2bc5b4a89aa5" />

---

## 🗺️ 3. Modelo Relacional

<img width="577" height="415" alt="Modelo Relacional Tienda" src="https://github.com/user-attachments/assets/d974c959-fc10-40c5-95d5-6899e52e3ffe" />

---

## 🖼️ 4. Codigo MySQL
```sql

CREATE DATABASE ej6_tienda_informatica;
USE ej6_tienda_informatica;

CREATE TABLE Cliente (
    codigo    INT PRIMARY KEY,
    nombre    VARCHAR(60) NOT NULL,
    apellidos VARCHAR(80) NOT NULL,
    direccion VARCHAR(150),
    telefono  VARCHAR(15)
);

CREATE TABLE Producto (
    codigo      INT PRIMARY KEY,
    descripcion VARCHAR(200) NOT NULL,
    precio      DECIMAL(10,2) NOT NULL,
    existencias INT NOT NULL
);

CREATE TABLE Compra (
    id_compra       INT PRIMARY KEY,
    codigo_cliente  INT  NOT NULL,
    codigo_producto INT  NOT NULL,
    fecha           DATE NOT NULL,
    FOREIGN KEY (codigo_cliente)  REFERENCES Cliente (codigo),
    FOREIGN KEY (codigo_producto) REFERENCES Producto (codigo)
);

CREATE TABLE Proveedor (
    codigo    INT PRIMARY KEY,
    nombres   VARCHAR(60) NOT NULL,
    apellidos VARCHAR(80) NOT NULL,
    direccion VARCHAR(150),
    provincia VARCHAR(60),
    telefono  VARCHAR(15)
);

CREATE TABLE Suministra (
    codigo_producto  INT NOT NULL,
    codigo_proveedor INT NOT NULL,
    PRIMARY KEY (codigo_producto, codigo_proveedor),
    FOREIGN KEY (codigo_producto)  REFERENCES Producto (codigo),
    FOREIGN KEY (codigo_proveedor) REFERENCES Proveedor (codigo)
);

```

---


[⬅️ Volver al índice de modelos](Modelos.md)
