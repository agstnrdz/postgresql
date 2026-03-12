# PostgreSQL
## Notas técnicas y teóricas
### Introducción

#### Introducción
```sql
SELECT *
FROM tabla
WHERE nombre = 'Rodolfo';
```

#### Primary key
```sql
-- Define el campo id como primary key
CREATE TABLE tabla(
idpersona int not null,
nombre varchar (20),
primary key (idpersona)
)

ALTER TABLE tabla
add primary key (idpersona)
```
#### Serial
```sql
-- Autoincrementar el campo definido como serial
CREATE TABLE tabla(
idtest serial primary key not null,
nombre varchar (20)
contacto varchar (10)
)
```
