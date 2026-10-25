## ✈️ Ejemplo 4: Sistema de Aerolínea

**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 1. Análisis del problema

Una aerolínea opera vuelos (cada uno con número, fecha, origen y destino), cada vuelo lo realiza un avión. Los pasajeros realizan reservas para un vuelo específico, indicando asiento y tarifa pagada en el momento de la reserva.

## 2. Diagrama Entidad-Relación

<img width="752" height="304" alt="Aeorolínea" src="https://github.com/user-attachments/assets/567d32d3-c4ce-4954-8c2f-1329b4193ffb" />

---

## 3. Modelo Relacional

<img width="539" height="425" alt="Modelo Aerolinia" src="https://github.com/user-attachments/assets/7fb856c8-c095-4b16-9759-c67305bad2f6" />


---

## 🖼️ 4. Codigo MySQL
```sql

Create Table Avion (
    id_avion Int Primary Key
);
 
Create Table Vuelo (
    numero   Varchar(10) Primary Key,
    fecha    Date Not Null,
    origen   Varchar(60) Not Null,
    destino  Varchar(60) Not Null,
    id_avion Int Not Null,
    Foreign Key (id_avion) References Avion (id_avion)
);
 
Create Table Pasajero (
    id_pasajero Int Primary Key,
    nombre      Varchar(100) Not Null
);
 
Create Table Reserva (
    id_pasajero Int Not Null,
    numero      Varchar(10) Not Null,
    asiento     Varchar(5)  Not Null,
    tarifa      Decimal(8,2) Not Null,
    Primary Key (id_pasajero, numero),
    Foreign Key (id_pasajero) References Pasajero (id_pasajero),
    Foreign Key (numero)      References Vuelo (numero)
);

```
---

[⬅️ Volver al índice de modelos](Modelos.md)
