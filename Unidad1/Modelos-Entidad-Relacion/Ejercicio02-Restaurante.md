# 🍽️ Ejercicio 2: Pedidos de Restaurante

**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 1. Análisis del problema

El restaurante necesita registrar los clientes, pedidos, platos, categorías y meseros. Cada pedido contiene varios platos, de los cuales se debe guardar la cantidad solicitada y el precio que tenían al momento de realizar el pedido.

El precio histórico es importante porque el precio actual de un plato puede cambiar sin modificar el valor de los pedidos anteriores.

## 2. Identificación de entidades y atributos

Las entidades identificadas en el sistema son las siguientes:

| Entidad | Descripción | Atributos |
|---|---|---|
| Cliente | Representa a las personas que realizan pedidos. | No especificados en el enunciado. |
| Pedido | Representa las solicitudes realizadas por los clientes. | No especificados en el enunciado. |
| Plato | Representa los platos ofrecidos por el restaurante. | No especificados en el enunciado. |
| Categoría | Permite clasificar los platos del restaurante. | No especificados en el enunciado. |
| Mesero | Representa al empleado encargado de atender los pedidos. | No especificados en el enunciado. |
| Detalle del pedido | Registra los platos incluidos en cada pedido. | Cantidad, precio histórico del plato. |

## 3. Relaciones y cardinalidades

| Relación | Descripción | Cardinalidad |
|---|---|---|
| Cliente - Pedido | Un cliente puede realizar varios pedidos y cada pedido corresponde a un cliente. | Uno a muchos (1:N). |
| Pedido - Plato | Un pedido puede contener varios platos y un plato puede aparecer en diferentes pedidos. | Muchos a muchos (N:M). |
| Categoría - Plato | Una categoría puede agrupar varios platos y cada plato pertenece a una categoría. | Uno a muchos (1:N). |
| Mesero - Pedido | Un mesero puede atender varios pedidos y cada pedido es atendido por un único mesero. | Uno a muchos (1:N). |

### Análisis de las relaciones

- **Cliente - Pedido:** Un cliente puede realizar diferentes pedidos, pero cada pedido está asociado a un único cliente.
- **Pedido - Plato:** Es una relación de muchos a muchos, ya que un pedido puede incluir varios platos y un plato puede formar parte de distintos pedidos. Se representa mediante la entidad intermedia `Detalle_Pedido`.
- **Categoría - Plato:** Una categoría puede contener varios platos, mientras que cada plato pertenece a una categoría.
- **Mesero - Pedido:** Un mesero puede atender varios pedidos, pero cada pedido es asignado a un único mesero.

## 4. Diagrama Entidad-Relación

El diagrama representa las entidades, sus relaciones y las cardinalidades correspondientes.

<img width="604" height="338" alt="restaurant" src="https://github.com/user-attachments/assets/40d523f2-261d-4221-b583-bce0574680d5" />

## 5. Conclusión

El modelo entidad-relación permite organizar la información del restaurante y establecer las relaciones entre clientes, pedidos, platos, categorías y meseros.

Además, la entidad `Detalle_Pedido` permite registrar la cantidad solicitada y el precio histórico de cada plato, garantizando que los cambios posteriores en los precios no alteren la información de los pedidos anteriores.

---

[⬅️ Volver al índice de modelos](Modelos.md)
