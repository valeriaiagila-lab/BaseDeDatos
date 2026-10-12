## 🏢 Ejercicio 10: Empresa

**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 🔎 1. Análisis del problema

La empresa necesita administrar sus departamentos, empleados, proyectos y el historial de salarios.

Cada empleado pertenece a un departamento y puede trabajar en varios proyectos. También existen empleados que supervisan a otros empleados. Se necesita registrar el historial salarial de cada empleado.

## 🏷️ 2. Identificación de entidades y atributos

| Entidad | Descripción |
|---|---|
| Departamento | Representa los departamentos de la empresa. |
| Empleado | Representa a los trabajadores. |
| Proyecto | Representa los proyectos de la empresa. |
| Historial de salario | Registra los salarios de los empleados a lo largo del tiempo. |

### 📋 Atributos identificados

- **Departamento:** identificador y nombre.
- **Empleado:** identificador y nombre.
- **Proyecto:** identificador y nombre.
- **Trabajo:** horas.
- **Historial de salario:** monto, fecha de inicio y fecha de fin.

## 🔗 3. Relaciones y cardinalidades

| Relación | Descripción | Cardinalidad según el diagrama |
|---|---|---|
| Departamento - Empleado | Los empleados pertenecen a departamentos. | 1:N |
| Empleado - Empleado | Algunos empleados supervisan a otros. | Relación recursiva |
| Empleado - Proyecto | Los empleados trabajan en proyectos. | N:M |
| Empleado - Historial de salario | Registra el historial salarial. | Según el diagrama original |

### 📝 Análisis de las relaciones

- **Departamento - Empleado:** La relación `Pertenece` conecta los empleados con sus departamentos.
- **Empleado - Empleado:** La relación `Supervisa` representa la supervisión entre empleados.
- **Empleado - Proyecto:** La relación `Trabaja` registra las horas dedicadas a los proyectos.
- **Empleado - Historial de salario:** La relación `Tiene` conecta los empleados con sus registros salariales.

## 🗺️ 4. Diagrama Entidad-Relación

<img width="659" height="243" alt="Empresa" src="https://github.com/user-attachments/assets/d41cc390-ddc0-4555-9358-9d255840df7c" />

## ✅ 5. Conclusión

El modelo permite organizar los departamentos, empleados y proyectos, así como representar la supervisión entre empleados y mantener el historial de salarios.

---

[⬅️ Volver al índice de modelos](Modelos.md)
