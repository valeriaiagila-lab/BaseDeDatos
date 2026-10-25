## 🎵 Ejercicio 7: Discos Musicales

----
**Asignatura:** Base de Datos  
**Tema:** Modelo Entidad-Relación

---

## 🔎 1. Enunciado

- La tienda vende discos de diferentes géneros musicales y cantantes.
- Cada género musical tiene un identificador.
- Cada disco tiene título, género musical, precio y cantante.
- De un cantante se registra el nombre y su país. Todo disco pertenece a un cantante y un cantante puede tener muchos discos. Además, un disco tiene un conjunto de canciones (identificador y título).
- Un disco tiene muchas canciones y una canción puede estar en varios discos. Interesa conocer la posición de una canción en un determinado disco.

## 🗺️ 2. Diagrama Entidad-Relación

<img width="999" height="411" alt="Tienda infromatica" src="https://github.com/user-attachments/assets/e67bb189-7fa3-4d08-a713-f63837c81f86" />

## 🗺️ 3. Modelo Relacional

<img width="623" height="465" alt="Modelo Relacional Discos" src="https://github.com/user-attachments/assets/c9326492-8625-4d6b-9752-dccb84e99398" />


---


## 🖼️ 4. Codigo MySQL
```sql
CREATE DATABASE ej7_discos_musicales;
USE ej7_discos_musicales;

CREATE TABLE Genero (
    id_genero VARCHAR(40) PRIMARY KEY
);

CREATE TABLE Cantante (
    id_cantante INT PRIMARY KEY,
    nombre      VARCHAR(100) NOT NULL,
    pais        VARCHAR(60)  NOT NULL
);

CREATE TABLE Disco (
    id_disco    INT PRIMARY KEY,
    titulo      VARCHAR(150) NOT NULL,
    precio      DECIMAL(8,2) NOT NULL,
    id_genero   VARCHAR(40)  NOT NULL,
    id_cantante INT NOT NULL,
    FOREIGN KEY (id_genero)   REFERENCES Genero (id_genero),
    FOREIGN KEY (id_cantante) REFERENCES Cantante (id_cantante)
);

CREATE TABLE Cancion (
    id_cancion INT PRIMARY KEY,
    titulo     VARCHAR(150) NOT NULL
);

CREATE TABLE Contiene (
    id_disco   INT NOT NULL,
    id_cancion INT NOT NULL,
    posicion   INT NOT NULL,
    PRIMARY KEY (id_disco, id_cancion),
    FOREIGN KEY (id_disco)   REFERENCES Disco (id_disco),
    FOREIGN KEY (id_cancion) REFERENCES Cancion (id_cancion)
);

```

---


[⬅️ Volver al índice de modelos](Modelos.md)
