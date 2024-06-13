# Sesion 2: REST-API - Metodo HTTP GET 

## Objetivo: 

        - Realizar pruebas de rendimiento para un REST-API - Metodo HTTP GET 


## Elaboracion de la practica: 

        1. Iniciar JMETER. 

        2. Sobre la carpeta Test Plan, Adicionar un Thread Group. Agregar la siguiente configuracion:

                - Name: Usuarios 
                - Number of Threads: 10 
                - Ramp-up period: 2 

![alt text](S2_1.png)

![alt text](S2_2.png)


        3. Sobre el Thread-Group Usuarios, crear un Sampler de tipo HTTP Request. Agregar la siguiente configuracion. 

                - Name: Get Method
                - HTTP Request: GET 
                - Path: /api/users
                - Parameters. 
                        Name: page, Value: 2 
                        Name: per_page, Value: 4 
                 
![alt text](S2_3.png)

![alt text](S2_4.png)


        4. Sobre el Thread-Group Usuarios, crear un Config Element de tipo HTTP Request Defaults. Agregar la siguiente configuracion. 

                - Name: HTTP Request Defaults
                - Server Name: reqres.in 

![alt text](S2_5.png)

![alt text](S2_6.png)


        5. Sobre el Thread-Group Usuarios, crear dos listeners de tipo View Results Tree y Summary Report. 

![alt text](S2_7.png)

![alt text](S2_8.png)

![alt text](S2_9.png)


        6. Ejecute los casos de prueba realizando click en la flecha verde. 

        7. Analice los resultados obtenidos en el View Results Tree y Summary Report 
