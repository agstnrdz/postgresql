# PostgreSQL
## Notas técnicas y teóricas

#### General
```sql
SELECT *
FROM tabla
WHERE nombre = 'Rodolfo'
AND edad > 9
GROUP BY nombre, salario, edad
HAVING salario > 1500
ORDER BY nombre

```

#### Primary key
```sql
-- Define el campo id como primary key
CREATE TABLE tabla(
idpersona int not null,
nombre varchar(20),
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
nombre varchar(20)
contacto varchar(10)
)
```

#### Default values
```sql
-- Definir valor por defecto en campo
CREATE TABLE tabla(
idtest serial primary key not null,
nombre varchar(20),
contacto varchar(20) default 'Desconocido'
)
```

#### Sum and count features
```sql
SELECT SUM(*)
SELECT COUNT(*)
FROM tabla
WHERE nombre like '%a%'
```

#### Unique
```sql
-- Restringir que un valor se repita en una columna
ALTER TABLE tabla
ADD CONSTRAINT UQ_salario
UNIQUE(salario)
```

#### Foreign key
```sql
-- Agregar una llave foránea para relacionar tablas
-- Ejemplo de dos tablas
SELECT * from tabla Campo(nombre, nid, salario)
SELECT * from empresas -- Campo(codigo)

-- Agregar un campo(int)
ALTER TABLE tabla
ADD codigo_empresa integer

-- 
ALTER TABLE tabla
ADD CONSTRAINT FKtest
FOREIGN KEY(codigo_empresa)
references empresas(codigo_empresa)

-- Agregar valores al campo
update tabla set codigoempresa = '2'

-- Agregar un feature de ejemplo
inser into tabla values ('Rodolfo','4','1500','5')
```
