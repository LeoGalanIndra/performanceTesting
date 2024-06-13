# Sesion 2: REST-API - Metodo HTTP POST 

## Objetivo: 

        - Realizar pruebas de rendimiento para un REST-API - Metodo HTTP POST


## Recursos

        - El recurso para realizar las pruebas es https://petstore.swagger.io/v2/user


## Elaboracion de la practica: 

        1. Iniciar JMETER. 

        2. Sobre la carpeta Test Plan, Adicionar un Thread Group. Agregar la siguiente configuracion:

                - Name: Usuarios 
                - Number of Threads: 5 
                - Ramp-up period: 100

![alt text](S3_1.png)


        3. Sobre el Thread-Group Usuarios, crear un Sampler de tipo HTTP Request. Agregar la siguiente configuracion. 

                - Name: Post Method
                - Protocol: https
                - Server Name: petstore.swagger.io
                - HTTP Request: POST 
                - Path: /v2/user
                - Body Data: ${myBody}

                        
                 
![alt text](S3_2.png)

        4. Sobre el HTTP Request creado (POST), adicionar un elemento Pre Processor de tipo User Parameters. Sobre el elemento creado, adicionar una variable Name: 'myBody' - User_1: 

                { 
                        "username": "testuser",
                        "firstName": "firstName",
                        "lastName": "lastName",
                        "email": "email@email.com",
                        "password": "password",
                        "phone": "987654321",
                        "userStatus": 1 
                } 

        5. Sobre el Thread-Group Usuarios agregar un Http Header Manager. Agregar dos atributos: 

                - accept: application/json
                - Content-Type: application/json

![alt text](S3_3.png)


        6. Sobre el Thread-Group Usuarios, crear dos listeners de tipo View Results Tree y Summary Report.

 ![alt text](S3_4.png)       


        7. Ejecute los casos de prueba realizando click en la flecha verde. 

        8. Analice los resultados obtenidos en el View Results Tree y Summary Report 