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
CREATE DATABASE ej4_aerolinea;
USE ej4_aerolinea;

CREATE TABLE Avion (
    id_avion INT PRIMARY KEY
);

CREATE TABLE Vuelo (
    numero   VARCHAR(10) PRIMARY KEY,
    fecha    DATE NOT NULL,
    origen   VARCHAR(60) NOT NULL,
    destino  VARCHAR(60) NOT NULL,
    id_avion INT NOT NULL,
    FOREIGN KEY (id_avion) REFERENCES Avion (id_avion)
);

CREATE TABLE Pasajero (
    id_pasajero INT PRIMARY KEY,
    nombre      VARCHAR(100) NOT NULL
);

CREATE TABLE Reserva (
    id_pasajero INT NOT NULL,
    numero      VARCHAR(10) NOT NULL,
    asiento     VARCHAR(5)  NOT NULL,
    tarifa      DECIMAL(8,2) NOT NULL,
    PRIMARY KEY (id_pasajero, numero),
    FOREIGN KEY (id_pasajero) REFERENCES Pasajero (id_pasajero),
    FOREIGN KEY (numero)      REFERENCES Vuelo (numero)
);

```
---

[⬅️ Volver al índice de modelos](Modelos.md)
