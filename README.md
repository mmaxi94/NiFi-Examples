# NiFi-Examples
Some NiFi flows integrated with ElasticSearch, Mongo, API's, CSV and more


## Loop Index Elasticsearch
El objetivo del flujo es leer todos los registros de un indice de ElasticSearch utilizando la API de Scroll y técnicas de corte de control. La cantidad de resultados devueltos por pagina es parametrizable. Para mas informacion: https://www.elastic.co/guide/en/elasticsearch/reference/current/scroll-api.html


## MongoDB to Postgres & Postgres to MongoDB
El objetivo del flujo es obtener los datos provenientes de una base MongoDB, cargar los registros en una base de datos relacional como Postgres y luego, transformar la informacion insertada en la tabla con el fin de convertirla nuevamente en el mismo formato del JSON original e insertarla en una nueva coleccion en MongoDB.
Para la carga inicial de la coleccion "students" de MongoDB, se utilizó el file "students.json" que, a fines practicos, se cargó manualmente a traves de Robo3T.
