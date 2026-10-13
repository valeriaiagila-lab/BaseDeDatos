## 🐾 Ejercicio 9: Veterinaria

----
# 🐾 Ejemplo 9: Veterinaria

**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 🔎 1. Análisis del problema

La clínica veterinaria necesita organizar la información de los propietarios, mascotas, personal, veterinarios, auxiliares y familiares de contacto.

Las mascotas pertenecen a propietarios y pasan consulta con veterinarios. Durante las consultas se registra un diagnóstico. También se almacena la información del familiar de contacto para emergencias.

## 🏷️ 2. Identificación de entidades y atributos

| Entidad | Descripción |
|---|---|
| Propietario | Representa a los propietarios de las mascotas. |
| Mascota | Representa a los animales atendidos. |
| Personal | Representa al personal de la clínica. |
| Veterinario | Representa al personal veterinario. |
| Auxiliar | Representa al personal auxiliar. |
| Familiar de contacto | Representa al contacto de emergencia del propietario. |

### 📋 Atributos identificados

- **Propietario:** cédula, apellidos, nombres, dirección y teléfonos.
- **Mascota:** identificador, nombre, fecha de nacimiento y tipo.
- **Personal:** código, cédula y nombre.
- **Veterinario:** fecha de alta y especialidad.
- **Auxiliar:** base de cotización.
- **Familiar de contacto:** cédula, nombre y teléfono.
- **Consulta:** fecha y diagnóstico.

## 🔗 3. Relaciones y cardinalidades

| Relación | Descripción | Cardinalidad o tipo |
|---|---|---|
| Propietario - Mascota | Los propietarios llevan mascotas a la clínica. | 1:N |
| Mascota - Veterinario | Las mascotas pasan consulta con veterinarios. | N:M |
| Propietario - Familiar de contacto | Relaciona al propietario con su familiar de contacto. | Según el diagrama original |
| Personal - Veterinario | Veterinario es un subtipo de Personal. | Herencia |
| Personal - Auxiliar | Auxiliar es un subtipo de Personal. | Herencia |

### 📝 Análisis de las relaciones

- **Propietario - Mascota:** La relación `Lleva` conecta los propietarios con sus mascotas.
- **Mascota - Veterinario:** La relación `Consulta` registra las consultas, la fecha y el diagnóstico.
- **Propietario - Familiar de contacto:** La relación `Contacto` conecta al propietario con su familiar de emergencia.
- **Personal - Veterinario y Auxiliar:** Representa una relación de herencia (generalización/especialización). `Veterinario` y `Auxiliar` son subtipos de `Personal`. Ambos heredan los atributos comunes de `Personal` y cada uno tiene sus propios atributos específicos.

## 🗺️ 4. Diagrama Entidad-Relación


En el diagrama, el triángulo de herencia representa la generalización o especialización entre `Personal` y sus subtipos:

<img width="820" height="521" alt="VETERINARIA1" src="https://github.com/user-attachments/assets/1c939069-a2eb-4d64-9296-5c95c702b65f" />


- **Personal:** entidad general o supertipo.
- **Veterinario:** subtipo que hereda los atributos de Personal y tiene los atributos específicos `fecha de alta` y `especialidad`.
- **Auxiliar:** subtipo que hereda los atributos de Personal y tiene el atributo específico `base de cotización`.

## ✅ 5. Conclusión

El modelo permite organizar la información de los propietarios, mascotas y personal de la clínica veterinaria. También permite registrar las consultas, sus diagnósticos y los datos del familiar de contacto.


---

[⬅️ Volver al índice de modelos](Modelos.md)
