# NiFi-Examples
Some NiFi flows integrated with ElasticSearch, Mongo, API's, CSV and more


## Loop Index Elasticsearch
El objetivo del flujo es leer todos los registros de un indice de ElasticSearch utilizando la API de Scroll y técnicas de corte de control. La cantidad de resultados devueltos por pagina es parametrizable. Para mas informacion: https://www.elastic.co/guide/en/elasticsearch/reference/current/scroll-api.html


## MongoDB to Postgres & Postgres to MongoDB
El objetivo del flujo es obtener los datos provenientes de una base MongoDB, cargar los registros en una base de datos relacional como Postgres y luego, transformar la informacion insertada en la tabla con el fin de convertirla nuevamente en el mismo formato del JSON original e insertarla en una nueva coleccion en MongoDB.
Para la carga inicial de la coleccion "students" de MongoDB, se utilizó el file "students.json" que, a fines practicos, se cargó manualmente a traves de Robo3T.

## MercadoLibre_Search_Products
El objetivo del flujo es generar una lista con los primeros N productos deseados en Mercadolibre, haciendo uso de la API de Search para productos y de conversion ratio USD/ARS para obtener el precio en dolares a tipo de cambio oficial. Los productos y cantidad a buscar se obtienen desde una tabla en SQL Server ([ver input_table.JPG](https://github.com/mmaxi94/NiFi-Examples/blob/main/MercadoLibre_Search_Products/input_table.JPG)). A partir de ello, se invocan las API de Mercadolibre hasta obtener el formato JSON deseado con los campos de interes. Se realizan validaciones con envio de mensajes de error por email en caso de que la busqueda por parametro a la API de productos falle ([ver email_error.JPG](https://github.com/mmaxi94/NiFi-Examples/blob/main/MercadoLibre_Search_Products/email_error.JPG)). El output del proceso es por un lado, un CSV conteniendo el detalle de todos los productos buscados ([ver Resultados_busqueda_2021-07-27-22-08-48.csv](https://github.com/mmaxi94/NiFi-Examples/blob/main/MercadoLibre_Search_Products/Resultados_busqueda_2021-07-27-22-08-48.csv)), y por otro lado, la carga en una tabla maestra de SQL Server conteniendo la misma informacion ([ver output_table.JPG](https://github.com/mmaxi94/NiFi-Examples/blob/main/MercadoLibre_Search_Products/output_table.JPG))
