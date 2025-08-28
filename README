# CRUD APP using AWS LAmbda, API Gateway and AWS Dynamo DB 

**AWS Lambda**

1. Nombre createBook y nodes 18.x
2. Si hago algún cambio en la función tengo que darle deploy
3. Ponemos el código de node js https://gist.github.com/ymulenll/67d7ae1ffb768d5d3deda1747dc4d4c8 
4. 


**API gateway**


1. Crear una HTTP API
2. Le damos Add Integration con lambda y me va a salir la función que yo había creado
3. Ponemos el nombre del API books-api
￼
4. Damos next y elegimos el verbo POST y el resource path que puede ser book y lo integramos con la función


￼


5. Todo lo demás queda por default y le damos crear

￼

6. Si damos click a la API podemos ver la URL del API

A este punto seria bueno probar el API a ver si está funcional, lo podemos probar con postman



￼



**Dynamo DB**


1. Nos vamos a DynamoDB y le damos create table
2. Le ponemos de nombre books y de partition key le ponemos id, todo lo de, mas queda default
3. En Explore table items puedo ver los itemes de la tabla existente 



￼
3. Para probarla (una vez actualizado el código en la funcion), debemos irnos a postman y generar un payload de json y en el body poner lo siguiente:


{
    "title":"bible",
    "author":"God"
}
￼

4. Si nos da el siguiente error, debemos actualizar el rol

{"message":"User: arn:aws:sts::255587935648:assumed-role/createBook-role-ft5i2b13/createBook is not authorized to perform: dynamodb:PutItem on resource: arn:aws:dynamodb:us-east-1:255587935648:table/books because no identity-based policy allows the dynamodb:PutItem action"}




**AWS CloudWatch**

1. Nos vamos a el evento creado
2. Damos click en monitor,  luego vamos a CloudWatch  logs
3. Dentro de log groups vamos a ver los logs de mi app



￼


1. Con search log group me sale tipo texto y es mas fácil ver los errores
￼


Agregar los permisos necesarios para que escriba en la BD


1. Me voy a la función lambda, doy click en configuración, luego en permisos
2. Ahi hay un rol existente con permisos a CloudWatch, damos click en el role para modificarlo

￼


3. Doy click en añadir permiso y luego en create inline policy
4. Creo la policy que necesito service dynamodb, action putitem
5. Especifico region y ARN
6. Genero un nombre para la policy y luego la creo 





(Los roles existentes son muy genéricos por eso yo debo crear algo mas especifico)

￼




*****

Finalmente debo borrar

- La función lambda
- El API Gateway creado
- La base de datos en Dynamo DB
- Los roles creados
- 

