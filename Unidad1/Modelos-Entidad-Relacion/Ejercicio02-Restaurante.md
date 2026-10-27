# 🍽️ Ejercicio 2: Pedidos de Restaurante

**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 1. Enunciado
Los clientes realizan pedidos que contienen varios platos con distinta cantidad. Los platos se agrupan en categorías. Cada pedido lo atiende un único mesero. El precio del plato debe registrarse tal como estaba al momento del pedido, aunque luego cambie.

## 2. Diagrama Entidad-Relación

El diagrama representa las entidades, sus relaciones y las cardinalidades correspondientes.


<img width="970" height="440" alt="Restaurant" src="https://github.com/user-attachments/assets/c43e7100-99cb-4e05-9666-864f0017f513" />



Además, la entidad `Detalle_Pedido` permite registrar la cantidad solicitada y el precio histórico de cada plato, garantizando que los cambios posteriores en los precios no alteren la información de los pedidos anteriores.

---

## 3. Modelo Relacional
<img width="449" height="463" alt="Modelo Relacional Restaurant" src="https://github.com/user-attachments/assets/46e1e187-dc20-48ca-8867-40560841ccf1" />



---

## 🖼️ 4. Codigo MySQL
```sql
Create Table Cliente (
    id_cliente Int Primary Key,
    nombre     Varchar(100) Not Null
);
 
Create Table Mesero (
    id_mesero Int Primary Key,
    nombre    Varchar(100) Not Null
);
 
Create Table Pedido (
    id_pedido  Int Primary Key,
    id_cliente Int Not Null,
    id_mesero  Int Not Null,
    Foreign Key (id_cliente) References Cliente (id_cliente),
    Foreign Key (id_mesero)  References Mesero (id_mesero)
);
 
Create Table Categoria (
    id_categoria Int Primary Key,
    nombre       Varchar(60) Not Null
);
 
Create Table Plato (
    id_plato     Int Primary Key,
    nombre       Varchar(100) Not Null,
    precio       Decimal(8,2) Not Null,
    id_categoria Int Not Null,
    Foreign Key (id_categoria) References Categoria (id_categoria)
);
 
Create Table Detalle_pedido (
    id_pedido       Int Not Null,
    id_plato        Int Not Null,
    cantidad        Int Not Null,
    precio_unitario Decimal(8,2) Not Null,
    Primary Key (id_pedido, id_plato),
    Foreign Key (id_pedido) References Pedido (id_pedido),
    Foreign Key (id_plato)  References Plato (id_plato)
);

 
```

---
## 🖼️ 5. Base de datos creada
<img width="232" height="223" alt="ejer2" src="https://github.com/user-attachments/assets/fbd40d54-f3f0-4022-8d50-127de20db5af" />


---



[⬅️ Volver al índice de modelos](Modelos.md)
