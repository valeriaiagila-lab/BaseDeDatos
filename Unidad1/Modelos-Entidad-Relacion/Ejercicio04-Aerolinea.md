✈️ Ejemplo 4: Sistema de Aerolínea

**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 1. Análisis del problema

Una aerolínea opera vuelos (cada uno con número, fecha, origen y destino), cada vuelo lo realiza un avión. Los pasajeros realizan reservas para un vuelo específico, indicando asiento y tarifa pagada en el momento de la reserva.


## 2. Identificación de entidades y atributos

| Entidad | Descripción |
|---|---|
| Pasajero | Representa a las personas que realizan reservas. |
| Vuelo | Representa los vuelos operados por la aerolínea. |
| Avión | Representa los aviones que realizan los vuelos. |

### Atributos identificados

- **Pasajero:** identificador y nombre.
- **Reserva:** asiento y tarifa.
- **Vuelo:** número, fecha, origen y destino.

## 3. Relaciones y cardinalidades

| Relación | Descripción | Cardinalidad según el diagrama |
|---|---|---|
| Pasajero - Vuelo | Los pasajeros reservan vuelos. | N:M |
| Vuelo - Avión | Relaciona los vuelos con los aviones. | N:1 |

### Análisis de las relaciones

- **Pasajero - Vuelo:** La relación `Reserva` registra el asiento y la tarifa de la reserva.
- **Vuelo - Avión:** La relación `Realiza` conecta los vuelos con los aviones.

## 4. Diagrama Entidad-Relación

<img width="752" height="304" alt="Aeorolínea" src="https://github.com/user-attachments/assets/567d32d3-c4ce-4954-8c2f-1329b4193ffb" />

## 5. Conclusión

El modelo permite organizar los vuelos, los pasajeros, las reservas y los aviones utilizados por la aerolínea.

---

[⬅️ Volver al índice de modelos](Modelos.md)
