# Informe general Platzi Movies
En este proyecto se realiza un informe general sobre una tienda de renta de peliculas ficticia llamada Platzi Movies, luego del proceso de ETL
## Desarrollo
Primero realizamos varias consultas que son necesarias para obtener la informacion que luego utilizaremos para crear un reporte con Power BI

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

* Top 10 las peliculas mas rentadas:

  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/bb61c328-39dd-4e94-94ad-9c913ea51a28)

  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/72ea641c-29f4-45e7-8b8f-7c5cf2b5a75c)

* Rentas por clasificacion:

  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/ba645c8e-9fe0-44b2-91d5-75afed16ceed)

  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/69675c46-2f75-466f-9a65-cda153f1c769)

* Rentas por ciudad:

  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/50649f97-0f8d-4b43-a58e-8aba17ed5be0)

  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/032a4f49-6c9b-48eb-997e-a003f43e6e59)

* Rentas en el tiempo:

  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/932f0ee9-e897-4e6e-884c-b28f79726fd4)

  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/f9b7e9e1-4c8b-47fc-9fd6-8c735b84e5f9)

### Graficos
Ahora simplemente recreamos los queries en Power BI para poder representarlos graficamente.
Sumandole algunos queries mas, llegamos al siguiente grafico interactivo:

![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/3be78bf8-475c-42df-96c7-61901c386cb4)

Al cual le podemos aplicar filtros, por ejemplo, por ciudad:
* Ventas en la cuidad de Mexicali

  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/df4ecd7f-f25c-4b32-bebe-6682e9954b82)

O por mes
* Ventas en Junio de 2005
  
  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/f815f124-0307-4f5d-a4f3-7d7cf33079ac)

Con la herramienta tooltips avanzados podemos crear información sobre herramientas que sean otros graficos, por ejemplo:
* Para cada clasificacion, rentas por categoria

  ![image](https://github.com/alejolemos3/final-project-postgresql-course/assets/105603884/4e1cf9bf-0eb4-4f74-a083-c6c7e25a6e89)

Por supuesto este reporte podria realizarse de distintas maneras y la base de datos posee gran variedad de posibles analisis y graficos, por ejemplo, ventas por empleados, clientes mas importantes, etc. Pero esto depende del problema que se busque solucionar.

Mi contacto es alejolemos213@gmail.com
