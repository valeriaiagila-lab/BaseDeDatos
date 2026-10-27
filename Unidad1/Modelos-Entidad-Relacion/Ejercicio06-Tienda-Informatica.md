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

Create Table Cliente (
    codigo    Int Primary Key,
    nombre    Varchar(60) Not Null,
    apellidos Varchar(80) Not Null,
    direccion Varchar(150),
    telefono  Varchar(15)
);
 
Create Table Producto (
    codigo      Int Primary Key,
    descripcion Varchar(200) Not Null,
    precio      Decimal(10,2) Not Null,
    existencias Int Not Null
);
 
Create Table Compra (
    id_compra       Int Primary Key,
    codigo_cliente  Int  Not Null,
    codigo_producto Int  Not Null,
    fecha           Date Not Null,
    Foreign Key (codigo_cliente)  References Cliente (codigo),
    Foreign Key (codigo_producto) References Producto (codigo)
);
 
Create Table Proveedor (
    codigo    Int Primary Key,
    nombres   Varchar(60) Not Null,
    apellidos Varchar(80) Not Null,
    direccion Varchar(150),
    provincia Varchar(60),
    telefono  Varchar(15)
);
 
Create Table Suministra (
    codigo_producto  Int Not Null,
    codigo_proveedor Int Not Null,
    Primary Key (codigo_producto, codigo_proveedor),
    Foreign Key (codigo_producto)  References Producto (codigo),
    Foreign Key (codigo_proveedor) References Proveedor (codigo)
);


```

---
## 🖼️ 5. Base de datos creada
---

<img width="292" height="209" alt="ejer6" src="https://github.com/user-attachments/assets/b5555973-0dbe-4dd5-b4a0-572236d72cd4" />

----


[⬅️ Volver al índice de modelos](Modelos.md)
