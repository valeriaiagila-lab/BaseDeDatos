## 💻 Ejercicio 6: Tienda Informática

----
**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 🔎 1. Análisis del problema

La tienda informática necesita administrar sus clientes, productos y proveedores.

Los clientes compran productos y cada compra registra su fecha. Los proveedores suministran los productos que comercializa la tienda.

## 🏷️ 2. Identificación de entidades y atributos

| Entidad | Descripción |
|---|---|
| Cliente | Registra la información de los clientes. |
| Producto | Registra los productos informáticos disponibles. |
| Proveedor | Registra la información de los proveedores. |
| Compra | Registra las compras realizadas y su fecha. |

### 📋 Atributos identificados

- **Cliente:** código, nombre, apellidos, dirección y teléfono.
- **Producto:** código, descripción, precio y existencias.
- **Proveedor:** código, nombres, apellidos, dirección, provincia y teléfono.
- **Compra:** fecha.

## 🔗 3. Relaciones y cardinalidades

| Relación | Descripción | Cardinalidad según el diagrama |
|---|---|---|
| Cliente - Producto | Registra las compras de productos. | N:M |
| Proveedor - Producto | Registra los productos suministrados. | N:M |

### 📝 Análisis de las relaciones

- **Cliente - Producto:** La relación `Compra` conecta los clientes con los productos y registra la fecha.
- **Proveedor - Producto:** La relación `Suministra` conecta los proveedores con los productos.

## 🗺️ 4. Diagrama Entidad-Relación

<img width="622" height="180" alt="Tienda" src="https://github.com/user-attachments/assets/ea69d7c1-cbbd-4b73-9eae-2bc5b4a89aa5" />

## ✅ 5. Conclusión

El modelo permite administrar los clientes, productos y proveedores, además de registrar las compras y las relaciones entre los productos y sus proveedores.

---

[⬅️ Volver al índice de modelos](Modelos.md)
