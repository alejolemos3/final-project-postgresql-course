# Informe general Platzi Movies
En este proyecto se realiza un informe general sobre una tienda de renta de peliculas ficticia llamada Platzi Movies, luego del proceso de ETL
## Desarrollo
Primero realizamos varias consultas que son necesarias para obtener la informacion que luego analizaremos graficamente con Power BI

### Queries
* Monto total en dolares de todas las rentas de la base de datos, independientemente de que hayan sido cobradas o no:

  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/7fcc5d9e-a034-4a2f-9b0d-7a95dc1a7878)
  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/2a92b1f1-7672-4b6d-aa23-1c53f942bdaf)

* Monto total en dolares de todos los cobros realizados:
  
  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/8484703a-d7a8-4de1-a9ca-361d7bc1d739)
  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/95d62f19-2304-426d-af38-484244aa08f5)

* A simple vista se detecta que los cobros realizados superan el valor de las rentas totales, es decir que los cobros pendientes totales son negativos:

  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/42d59f98-c881-47fc-9db4-a0b48db7dcbd)
  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/1339bc05-c30f-4016-bdef-f939e1658190)

  Efectivamente, los cobros pendientes totales son -18315 aproximadamente lo cual debe ser un error de la base de datos.

  Seleccionando el precio de la renta y el valor del pago relacionado con la misma para cada fila vemos que hay pagos (cantidad) realizados por un valor mayor al de la renta (precio_renta), por eso los pagos pendientes totales son negativos:

  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/bf352537-7d35-4a26-bb16-c4b35dc1e016)
  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/747fe6bd-76d0-4678-b39a-13c626115411)

* Para obtener los pagos pendientes reales hacemos la siguiente consulta:

  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/53f489f8-4ed9-43c1-b2d6-a7ed6fe59c2e)
  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/e6da7fb8-1e0a-45ba-ae58-93bcec11fe90)


