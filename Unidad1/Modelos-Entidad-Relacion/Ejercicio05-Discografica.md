## 🎤 Ejercicio 5: Empresa Discográfica

------
**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 🔎 1. Enunciado
Una empresa discográfica necesita modelar los datos sobre sus diferentes recursos según las siguientes características:

- **Manager:** de cada mánager se almacena un identificador de manager y su nombre. Un manager representa a una serie de artistas.

- **Artista:** un artista es representado por un manager. De los artistas se almacena su nombre completo (usando un único atributo) y su NIF.

- **Evento de promoción:** los artistas participan en eventos de promoción para dar a conocer sus trabajos. En un evento de promoción pueden participar varios artistas. De un evento se almacena un identificador único, la fecha de celebración y el número de asistentes.


## 🗺️ 2. Diagrama Entidad-Relación

<img width="807" height="260" alt="Discografia" src="https://github.com/user-attachments/assets/d75745b7-8776-4908-873b-fc48502a541d" />


---

## 🗺️ 3. Modelo Relacional

<img width="727" height="441" alt="modelo Discografia" src="https://github.com/user-attachments/assets/f99ab980-036b-44fc-a759-f2530d7e2ff8" />


---

## 🖼️ 4. Codigo MySQL
```sql
CREATE DATABASE ej5_discografica;
USE ej5_discografica;

CREATE TABLE Manager (
    identificador INT PRIMARY KEY,
    nombre        VARCHAR(100) NOT NULL
);

CREATE TABLE Artista (
    NIF        VARCHAR(9) PRIMARY KEY,
    nombre     VARCHAR(120) NOT NULL,
    id_manager INT NOT NULL,
    FOREIGN KEY (id_manager) REFERENCES Manager (identificador)
);

CREATE TABLE Evento_promocion (
    identificador     INT PRIMARY KEY,
    fecha_celebracion DATE NOT NULL,
    numero_asistentes INT  NOT NULL
);

CREATE TABLE Participa (
    NIF       VARCHAR(9) NOT NULL,
    id_evento INT NOT NULL,
    PRIMARY KEY (NIF, id_evento),
    FOREIGN KEY (NIF)       REFERENCES Artista (NIF),
    FOREIGN KEY (id_evento) REFERENCES Evento_promocion (identificador)
);

```

---

[⬅️ Volver al índice de modelos](Modelos.md)
