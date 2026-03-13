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

-- Insertar valores
INSERT INTO tabla(campos)
VALUES ('','','','')

-- Agregar una columna nueva
ALTER TABLE tabla
ADD COLUMN columna varchar(20)

-- Actualizar una columna
UPDATE tabla
SET pais = 'Argentina'
WHERE id = 1;
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
SELECT * from tabla --campos: (nombre, nid, salario)
SELECT * from empresas -- campo: (codigo)

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

# Functions to manage strings
```sql
-- Consultar el largo del texto
char_length

-- Convertir caracteres en mayúscula
upper(string)

-- Convertir caracretes en minúscula
lower(string)

-- 
```
