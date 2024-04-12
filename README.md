# **Taller Sobre Consultas a Bases de Datos**

**Estudiante:** Duván Camilo Arenas Rodríguez - j1

#### Se presenta la siguiente base de Datos: 



#### ![](C:\Users\dccar\AppData\Roaming\Typora\typora-user-images\image-20240411083123700.png)



#### Realizar las siguientes inserciones de datos:



1. fabricante (1, 'Asus')

```mysql
NSERT INTO fabricante (codigo, nombre) VALUES (1, 'Asus');
```



2. fabricante (2, 'Lenovo')

```mysql
INSERT INTO fabricante (codigo, nombre) VALUES (2, 'Lenovo');
```



3. fabricante (3, 'Hewlett - Packard')

```mysql
INSERT INTO fabricante (codigo, nombre) VALUES (3, 'Hewlett - Packard');
```



4. fabricante (4, 'Samsung')

```mysql
INSERT INTO fabricante (codigo, nombre) VALUES (4, 'Samsung');
```



5. fabricante (5, 'Seagate')

```mysql
INSERT INTO fabricante (codigo, nombre) VALUES (5, 'Seagate');
```



6. fabricante (6, 'Crucial')

```mysql
INSERT INTO fabricante (codigo, nombre) VALUES (5, 'Seagate');
```



7. fabricante (7, 'Gigabyte')

```mysql
INSERT INTO fabricante (codigo, nombre) VALUES (7, 'Gigabyte');
```



8. fabricante (8, 'Huawei')

```mysql
INSERT INTO fabricante (codigo, nombre) VALUES (8, 'Huawei');
```



9. fabricante (9, 'Huawei')

```mysql
INSERT INTO fabricante (codigo, nombre) VALUES (9, 'Huawei');
```



10. producto (1, 'Disco duro SATA3 1TB', 86.99, 5)

```mysql
INSERT INTO producto (codigo, nombre, precio, codigo_fabricante) VALUES (1, 'Disco duro SATA3 1TB', 86.99, '5');
```



11. producto (2, 'Memoria RAM DDR4 8GB', 120, 6)

```mysql
INSERT INTO producto (codigo, nombre, precio, codigo_fabricante) VALUES (2, 'Memoria RAM DDR4 8GB', 120, 6);
```



12. producto (3, 'Disco SSD 1 TB', 150.99, 4)

    ```mysql
    INSERT INTO producto (codigo, nombre, precio, codigo_fabricante) VALUES (3, '150.99', 4);
    ```

    

13. producto (4, 'GeForce GTX 1050Ti', 185, 7)

    ```mysql
    INSERT INTO producto (codigo, nombre, precio, codigo_fabricante) VALUES (4, 'GeForce GTX 1050Ti', 185, 7);
    ```

    

14. producto (4, 'GeForce GTX 1050Ti', 185, 7)

    ```mysql
    INSERT INTO producto (codigo, nombre, precio, codigo_fabricante) VALUES (4, 'GeForce GTX 1050Ti', 185, 7);
    ```

    

15. producto (5, 'GeForce GTX 1080 Xtreme', 755, 6)

    ```mysql
    INSERT INTO producto (codigo, nombre, precio, codigo_fabricante) VALUES (5, 'GeForce GTX 1080 Xtreme', 755, 6);
    ```

    

16. producto (6, 'Monitor 24 LED Full HD', 202, 1)

    ```mysql
    INSERT INTO producto (codigo, nombre, precio, codigo_fabricante) VALUES (6, 'Monitor 24 LED Full HD', 202, 1);
    ```

    

17. producto (7, 'Monitor 27 LED Full HD', 245.99, 1)

    ```mysql
    INSERT INTO producto (codigo, nombre, precio, codigo_fabricante) VALUES (7, 'Monitor 27 LED Full HD', 245.99, 1);
    ```

    

18. producto (8, 'Portátil Yoga 520', 559, 2)

    ```mysql
    INSERT INTO producto (codigo, nombre, precio, codigo_fabricante) VALUES (8, 'Portátil Yoga 520', 559, 2);
    ```

    

19. producto (9, 'Portátil Ideapad 320', 444, 2)

    ```mysql
    INSERT INTO producto (codigo, nombre, precio, codigo_fabricante) VALUES (9, 'Portátil Ideapad 320', 444, 2);
    ```

    

20. producto (10, 'Impresora HP Deskjet 3720', 59.99, 3)

    ```mysql
    INSERT INTO producto (codigo, nombre, precio, codigo_fabricante) VALUES (10, 'Impresora HP Deskjet 3720', 59.99, 3);
    ```

    

21. producto (11, 'Impresora HP Laserjet Pro M26nw', 180, 3)

    ```mysql
    INSERT INTO producto (codigo, nombre, precio, codigo_fabricante) VALUES (11, 'Impresora HP Laserjet Pro M26nw', 180, 3);
    ```

    

#### Realizar las siguientes consultas:

1. Lista el nombre de todos los productos que hay en la tabla `producto`

   ```mysql
   SELECT nombre
   FROM producto
   ```

   

2. Lista los nombres y los precios de todos los productos de la tabla `producto`

   ```mysql
   SELECT nombre, precio
   FROM producto
   ```



3. Lista todas las columnas de la tabla `producto`.

   ```mysql
   SELECT codigo, nombre, precio, codigo_fabricante
   FROM producto
   ```



4. Lista el nombre de los productos, el precio en euros y el precio en dólares estadounidenses (USD).

   ```mysql
   SELECT nombre, precio, precio * 1.12 AS euros
   FROM producto
   ```

   

5. Lista el nombre de los productos, el precio en euros y el precio en dólares estadounidenses (USD). Utiliza los siguientes alias para las columnas: `nombre de producto`, `euros`, `dólares`.

   ```mysql
   SELECT nombre AS nombre_producto, precio AS dolares, precio * 1.12 AS euros
   FROM producto 
   ```



6. Lista los nombres y los precios de todos los productos de la tabla `producto`, convirtiendo los nombres a mayúscula.

   ```mysql
   SELECT UPPER(nombre), precio
   FROM producto
   ```



7. Lista los nombres y los precios de todos los productos de la tabla `producto`, convirtiendo los nombres a minúscula

   ```mysql
   SELECT LOWER(nombre), precio
   FROM producto
   ```

   

8. Lista el nombre de todos los fabricantes de una columna, y en otra columna obtenga en mayúsculas los dos primeros caracteres del nombre del fabricante

   ```mysql
   SELECT nombre, UPPER(SUBSTRING(nombre, 1, 2))
   FROM fabricante
   ```

   

9. Lista los nombres y los precios de todos los productos de la tabla `producto `, redondeando el valor del precio.

   ```mysql
   SELECT nombre, ROUND(precio)
   FROM producto
   ```

   

10. Lista los nombres y los precios de todos los productos de la tabla producto, truncando el valor del precio para mostrarlo sin ninguna cifra decimal.

    ```mysql
    SELECT nombre, TRUNCATE(precio, 0)
    FROM producto
    ```



11. Lista el identificador de los fabricantes que tienen productos en la tabla `producto`

    ```mysql
    SELECT fabricante.codigo 
    FROM fabricante, producto
    WHERE fabricante.codigo = producto.codigo_fabricante
    ```

    

12. Lista el identificador de los fabricantes que tienen productos en la tabla `producto`, eliminando los identificadores que aparecen repetidos.

    ```mysql
    SELECT DISTINCT fabricante.codigo
    FROM fabricante, producto
    WHERE fabricante.codigo = producto.codigo_fabricante
    ```

    

13. Lista los nombres de los fabricantes ordenados de forma ascendente.

    ```mysql
    SELECT nombre 
    FROM fabricante
    ORDER BY nombre ASC
    ```



14. Lista los nombres de los fabricantes ordenados de forma descendente.

    ```mysql
    SELECT nombre
    FROM fabricante
    ORDER BY nombre DESC
    ```

    

15. Lista los nombres de los productos ordenados en primer lugar por el nombre de forma ascendente y en segundo lugar por el precio de forma descendente.

    ```mysql
    SELECT nombre, precio
    FROM producto
    ORDER BY nombre ASC, precio DESC
    ```



16. Devuelve una lista con las 5 primeras filas de la tabla `fabricante`.

    ```mysql
    SELECT codigo, nombre
    FROM fabricante
    LIMIT 5
    ```

    

17. Devuelve una lista con 2 filas a partir de la cuarta fila de la tabla fabricante. La cuarta fila también se debe incluir en la respuesta.

    ```mysql
    SELECT codigo, nombre
    FROM fabricante
    LIMIT 2 OFFSET 3
    ```



18. Lista el nombre y el precio del producto más barato. (Utilice solamente las
    cláusulas ORDER BY y LIMIT)

    ```mysql
    SELECT nombre, precio
    FROM producto
    ORDER BY precio ASC
    LIMIT 1
    ```

    

19. Lista el nombre y el precio del producto más caro. (Utilice solamente las cláusulas ORDER BY y LIMIT)

    ```mysql
    SELECT nombre, precio
    FROM producto
    ORDER BY precio DESC
    LIMIT 1
    ```



20. Lista el nombre de todos los productos del fabricante cuyo identificador de fabricante es igual a 2.

    ```mysql
    SELECT nombre 
    FROM producto
    WHERE codigo_fabricante = 2
    ```



21. Lista el nombre de los productos que tienen un precio menor o igual a 120€.

    ```mysql
    SELECT nombre
    FROM producto
    WHERE precio <= 120
    ```

    

22. Lista el nombre de los productos que tienen un precio mayor o igual a 400€.

    ```mysql
    SELECT nombre
    FROM producto
    WHERE precio >= 400
    ```

    

23. Lista el nombre de los productos que no tienen un precio mayor o igual a 400€.

    ```mysql
    SELECT nombre
    FROM producto
    WHERE precio < 400
    ```

    

24. Lista todos los productos que tengan un precio entre 80€ y 300€. Sin utilizar el operador BETWEEN.

    ```mysql
    SELECT nombre
    FROM producto
    WHERE precio BETWEEN 80 AND 300
    ```



25. Lista todos los productos que tengan un precio entre 60€ y 200€. Utilizando el operador BETWEEN.

    ```mysql
    SELECT nombre
    FROM producto
    WHERE precio BETWEEN 60 AND 200
    ```



26. Lista todos los productos que tengan un precio mayor que 200€ y que el identificador de fabricante sea igual a 6.

    ```mysql
    SELECT nombre
    FROM producto
    WHERE precio > 200 AND codigo_fabricante = 6
    ```

    

27. Lista todos los productos donde el identificador de fabricante sea 1, 3 o 5. Sin utilizar el operador IN.

    ```mysql
    SELECT
    FROM producto
    WHERE codigo_fabricante = 1 OR codigo_fabricante = 3 OR codigo_fabricante = 5
    ```

    

28. Lista todos los productos donde el identificador de fabricante sea 1, 3 o 5. Utilizando el operador IN.

    ```mysql
    SELECT nombre
    FROM producto
    WHERE codigo_fabricante IN (1, 3, 5)
    ```



29. Lista el nombre y el precio de los productos en céntimos (Habrá que multiplicar por 100 el valor del precio). Cree un alias para la columna que contiene el precio que se llame céntimos.

    ```mysql
    SELECT nombre, precio * 100 AS centimos
    FROM producto
    ```

    

30. Lista los nombres de los fabricantes cuyo nombre empiece por la letra S.

    ```mysql
    SELECT nombre
    FROM fabricante
    WHERE nombre LIKE 'S%'
    ```

    

31. Lista los nombres de los fabricantes cuyo nombre termine por la vocal e.

    ```mysql
    SELECT nombre
    FROM fabricante
    WHERE nombre LIKE '%e'
    ```

    

32. Lista los nombres de los fabricantes cuyo nombre contenga el carácter w.

    ```mysql
    SELECT nombre
    FROM fabrica
    WHERE nombre LIKE '%w%'
    ```

    

33. Lista los nombres de los fabricantes cuyo nombre sea de 4 caracteres.

    ```mysql
    SELECT nombre
    FROM fabrica
    WHERE LENGTH(nombre) = 4 
    ```

    

34. Devuelve una lista con el nombre de todos los productos que contienen la cadena `Portátil` en el nombre.

    ```mysql
    SELECT nombre
    FROM productos
    WHERE nombre LIKE '%Portátil%'
    ```

    

35. Devuelve una lista con el nombre de todos los productos que contienen la cadena `Monitor` en el nombre y tienen un precio inferior a 215 €.

    ```mysql
    SELECT nombre
    FROM productos
    WHERE nombre LIKE '%Monitor%'AND precio < 215
    ```

    

36. Lista el nombre y el precio de todos los productos que tengan un precio mayor o igual a 180€. Ordene el resultado en primer lugar por el precio (en orden descendente) y en segundo lugar por el nombre (en orden ascendente).

    ```mysql
    SELECT nombre, precio
    FROM producto
    WHERE precio >= 180 
    ORDER BY precio DESC, nombre ASC
    ```

    

#### Consultas Multitabla (composición interna)

1. Devuelve una lista con el nombre del producto, precio y nombre de fabricante de todos los productos de la base de datos.

   ```mysql
   SELECT producto.nombre, producto.precio, fabrica.codigo 
   FROM producto, fabricante
   WHERE producto.codigo_fabricante = fabricante.codigo
   ```



2. Devuelve una lista con el nombre del producto, precio y nombre de fabricante de todos los productos de la base de datos. Ordene el resultado por el nombre del fabricante, por orden alfabético.

   ```mysql
   SELECT producto.nombre, producto.precio, fabricante.nombre
   FROM producto, fabricante
   WHERE Producto.codigo_fabricante = fabricante.codigo
   ORDER BY fabrica.nombre ASC
   ```

   

3. Devuelve una lista con el identificador del producto, nombre del producto, identificador del fabricante y nombre del fabricante, de todos los productos de la base de datos.

   ```mysql
   SELECT producto.codigo, producto.nombre, fabricante.codigo, fabricante.nombre
   FROM producto
   WHERE producto.codigo_fabricante = fabricante.codigo
   ```

   

4. Devuelve el nombre del producto, su precio y el nombre de su fabricante, del producto más barato.

   ```mysql
   SELECT producto.nombre, producto.precio, fabricante.nombre
   FROM producto, fabricante
   WHERE producto.codigo_fabricante = fabricante.codigo
   ORDER BY producto.precio ASC
   LIMIT 1
   ```



5. Devuelve el nombre del producto, su precio y el nombre de su fabricante, del producto más caro.

   ```mysql
   SELECT producto.nombre, producto.precio, fabricante.nombre
   FROM producto, fabricante
   WHERE producto.codigo_fabricante = fabricante.codigo
   ORDER BY DESC
   LIMIT 1
   ```

   

6. Devuelve una lista de todos los productos del fabricante Lenovo.

   ```mysql
   SELECT producto.nombre
   FROM producto, fabricante
   WHERE producto.codigo_fabricante = fabricante.codigo AND fabricante.nombre = 'Lenovo'
   ```



7. Devuelve una lista de todos los productos del fabricante Crucial que tengan un precio mayor que 200€.

   ```mysql
   SELECT producto.nombre 
   FROM producto, fabricante
   WHERE producto.codigo_fabricante = fabricante.codigo AND fabricante.nombre = 'Crucial' AND producto.precio > 200
   ```

   

8. Devuelve un listado con todos los productos de los fabricantes Asus, Hewlett-Packard y Seagate. Sin utilizar el operador IN.

   ```mysql
   SELECT producto.nombre
   FROM producto, fabricante
   WHERE producto.codigo_fabricante = fabricante.codigo AND fabricante.nombre = 'Asus' OR fabricante.nombre = 'Hewlett-Packard' OR fabricante.nombre = 'Seagate'
   ```

   

9. Devuelve un listado con todos los productos de los fabricantes Asus, Hewlett-Packard y Seagate. Utilizando el operador IN.

   ```mysql
   SELECT producto.nombre
   FROM producto, fabricante
   WHERE producto.codigo_fabricante = fabricante.codigo AND fabricante.nombre IN ('Asus', 'Hewlett-Packard', 'Seagate')
   ```



10. Devuelve un listado con el nombre y el precio de todos los productos de los fabricantes cuyo nombre termine por la vocal e.

    ```mysql
    SELECT producto.nombre
    FROM producto, fabricante
    WHERE producto.codigo_fabricante = fabricante.codigo AND fabricante.nombre LIKE '%e'
    ```

    

11. Devuelve un listado con el nombre y el precio de todos los productos cuyo nombre de fabricante contenga el carácter w en su nombre.

    ```mysql
    SELECT producto.nombre
    FROM producto, fabricante
    WHERE producto.codigo_fabricante = fabricante.codigo AND fabricante.nombre LIKE '%w%'
    ```



12. Devuelve un listado con el nombre de producto, precio y nombre de fabricante, de todos los productos que tengan un precio mayor o igual a 180€. Ordene el resultado en primer lugar por el precio (en orden descendente) y en segundo lugar por el nombre (en orden ascendente)

    ```mysql
    SELECT producto.nombre, producto.precio, fabricante.nombre
    FROM producto, fabricante
    WHERE producto.codigo_fabricante = fabricante.codigo AND producto.precio >= 180
    ORDER BY producto.precio DESC, producto.nombre ASC
    ```

    

13. Devuelve un listado con el identificador y el nombre de fabricante, solamente de aquellos fabricantes que tienen productos asociados en la base de datos.

    ```mysql
    SELECT DISTINCT fabricante.codigo, fabricante.nombre
    FROM producto, fabricante
    WHERE fabricante.codigo = producto.codigo_fabricante
    ```

    

