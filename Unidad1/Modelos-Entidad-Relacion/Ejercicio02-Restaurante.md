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



--


[⬅️ Volver al índice de modelos](Modelos.md)
