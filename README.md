# PostgreSQL
## Notas técnicas y teóricas
### Introducción

#### 
```sql
SELECT *
FROM tabla
WHERE nombre = 'Rodolfo';
```

#### Primary key
```sql
CREATE TABLE tabla(
idpersona int not null,
nombre varchar (20),
primary key (idpersona)
)

ALTER TABLE tabla
add primary key (idpersona)
```
