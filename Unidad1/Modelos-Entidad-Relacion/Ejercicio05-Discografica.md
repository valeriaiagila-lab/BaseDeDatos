##🎤 Ejercicio 5: Empresa Discográfica
------
**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 🔎 1. Análisis del problema

La empresa discográfica necesita organizar la información de sus mánagers, artistas y eventos de promoción.

Los mánagers representan a artistas y los artistas participan en eventos para promocionar sus trabajos.

## 🏷️ 2. Identificación de entidades y atributos

| Entidad | Descripción |
|---|---|
| Manager | Representa a los mánagers de los artistas. |
| Artista | Representa a los artistas de la empresa. |
| Evento de promoción | Registra los eventos de promoción. |

### 📋 Atributos identificados

- **Manager:** identificador y nombre.
- **Artista:** nombre completo y NIF.
- **Evento de promoción:** identificador, fecha de celebración y número de asistentes.

## 🔗 3. Relaciones y cardinalidades

| Relación | Descripción | Cardinalidad según el diagrama |
|---|---|---|
| Manager - Artista | Los mánagers representan artistas. | 1:N |
| Artista - Evento de promoción | Los artistas participan en eventos. | N:M |

### 📝 Análisis de las relaciones

- **Manager - Artista:** La relación `Representa` conecta al mánager con los artistas.
- **Artista - Evento de promoción:** La relación `Participa` registra la participación de los artistas en los eventos.

## 🗺️ 4. Diagrama Entidad-Relación

<img width="597" height="164" alt="Manager" src="https://github.com/user-attachments/assets/8781cabf-8be7-40d9-9d07-f3daa3f30331" />

## ✅ 5. Conclusión

El modelo permite organizar los artistas, sus mánagers y los eventos de promoción en los que participan.

---

[⬅️ Volver al índice de modelos](Modelos.md)
