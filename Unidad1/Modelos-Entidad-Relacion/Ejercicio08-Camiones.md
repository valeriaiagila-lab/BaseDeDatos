## 🚚 Ejercicio 8: Camiones
**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 🔎 1. Análisis del problema

La empresa de transporte necesita administrar los camioneros, paquetes, provincias y camiones utilizados para realizar las entregas.

Se registran los datos de los camioneros, las características de los paquetes, las provincias de destino y los camiones que conducen los camioneros en diferentes fechas.

## 🏷️ 2. Identificación de entidades y atributos

| Entidad | Descripción |
|---|---|
| Camionero | Representa a los encargados de transportar los paquetes. |
| Paquete | Representa los paquetes transportados. |
| Provincia | Representa las provincias de destino. |
| Camión | Representa los camiones utilizados. |

### 📋 Atributos identificados

- **Camionero:** cédula, nombre, teléfono, dirección, salario y población.
- **Paquete:** código, descripción, destinatario y dirección del destinatario.
- **Provincia:** código y nombre.
- **Camión:** matrícula, modelo, tipo y potencia.
- **Relación Conduce:** fecha.

## 🔗 3. Relaciones y cardinalidades

| Relación | Descripción | Cardinalidad según el diagrama |
|---|---|---|
| Provincia - Paquete | Registra la provincia a la que llega cada paquete. | 1:N |
| Camionero - Paquete | Registra la distribución de los paquetes. | 1:N |
| Camionero - Camión | Registra qué camioneros conducen los camiones. | N:M |

### 📝 Análisis de las relaciones

- **Provincia - Paquete:** La relación `Llega` conecta las provincias con los paquetes.
- **Camionero - Paquete:** La relación `Distribuye` registra qué camionero distribuye cada paquete.
- **Camionero - Camión:** La relación `Conduce` registra los camiones conducidos por los camioneros y la fecha correspondiente.

## 🗺️ 4. Diagrama Entidad-Relación

<img width="583" height="372" alt="Camiones" src="https://github.com/user-attachments/assets/91c10515-327b-4d35-a0e7-1c76cc76c038" />

## ✅ 5. Conclusión

El modelo permite organizar la información de los camioneros, paquetes, provincias y camiones, incluyendo las fechas de conducción.

---

[⬅️ Volver al índice de modelos](Modelos.md)
