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

Create Table Genero (
    id_genero Varchar(40) Primary Key
);
 
Create Table Cantante (
    id_cantante Int Primary Key,
    nombre      Varchar(100) Not Null,
    pais        Varchar(60)  Not Null
);
 
Create Table Disco (
    id_disco    Int Primary Key,
    titulo      Varchar(150) Not Null,
    precio      Decimal(8,2) Not Null,
    id_genero   Varchar(40)  Not Null,
    id_cantante Int Not Null,
    Foreign Key (id_genero)   References Genero (id_genero),
    Foreign Key (id_cantante) References Cantante (id_cantante)
);
 
Create Table Cancion (
    id_cancion Int Primary Key,
    titulo     Varchar(150) Not Null
);
 
Create Table Contiene (
    id_disco   Int Not Null,
    id_cancion Int Not Null,
    posicion   Int Not Null,
    Primary Key (id_disco, id_cancion),
    Foreign Key (id_disco)   References Disco (id_disco),
    Foreign Key (id_cancion) References Cancion (id_cancion)
);

```

---
## 🖼️ 5. Base de datos creada

<img width="250" height="184" alt="ejer7" src="https://github.com/user-attachments/assets/ffb628a5-37a3-42cc-b8c0-b87945c973ef" />


---


[⬅️ Volver al índice de modelos](Modelos.md)
