# Sesion 4: SCRIPTING 

## Objetivo: 

        - Realizar pruebas de rendimiento al realizar una rutina en un portal web. 


## Recursos

        - El recurso para realizar las pruebas es https://petstore.swagger.io/v2/user


## Elaboracion de la practica: 

        1. Iniciar JMETER. 

        2. Sobre la carpeta Test Plan, Adicionar un Thread Group. Agregar la siguiente configuracion:

                - Name: Usuarios 
                - Number of Threads: 1 
                - Ramp-up period: 1

![alt text](S4_1.png)


        3. Sobre el Test Plan, adicionar un elemento Non-Test Element de tipo HTTP(S) Test Script Recorder.   

![alt text](S4_2.png)      


        4. Configuramos el puerto 8888 en el navegador Firefox. Ingrese al navegador en la ruta Settings -> Connection Settings -> Manual proxy configuration (En espanol, Ajustes -> Configuracion de conexion -> Configuracion Manual del proxy), se adiciona: 

                HTTP Proxy: localhost 
                Port: 8888 

![alt text](S4_3.png)   


#### TIP Colocar en el buscador de los ajustes de Firefox la palabra 'proxy'

        5. Sobre el elemento HTTP(S) Test Script Recorder. Adicionar 

                Target Controller -> Thread Group creado anteriormente (Usuarios). 
                En la pestana Request Filtering agregamos una variable en URL Patterns to Exclude de tipo Add Suggested Excludes. 
                 
![alt text](S4_4.png) 

![alt text](S4_5.png) 


        6. Sobre el Thread-Group Usuarios, crear dos listeners de tipo View Results Tree y Summary Report.

        7. Agregar un Http Cookie Manager. 

![alt text](S4_6.png)


        8. El script guarda una rutina o proceso el cual es reejecutable. 

        A continuacion, vamos a generar un script con la siguiente rutina: 

        a. Ingresar al web page del navegador de Firefox

        http://www.testingyes.com/onlineshop/

        b. Dar click en Sign In 

        c. Ingresar con las credenciales 

           test1@testingyes.com/test12345   
       
        d. Seleccionar la pestana Accesories 

        e. Seleccionar un producto 

        f. Click en checkout 

        g. Proceder con la compra 

        h. En el checkout desistir de la compra 

        i. Realizar sign out. 

        A medida que ejecutemos cada paso del script, se sugiere cambiar el nombre de la transaccion. 

### Creacion del script 

        Dar click en Start que aparece en el HTTP Test Script Recoder. Aparece un cuadro de dialogo el cual permite controlar las transacciones ejecutadas (Recorder: Transactions Control). 
        

#### Ejecucion de la rutina. 

        Para empezar, en el nombre de la transaccion colocamos Home page - 

![alt text](S4_7.png)

       Ingresamos a la url indicada. Se continua con los pasos. 

![alt text](S4_8.png)

![alt text](S4_9.png)

        Al finalizar la rutina, volvemos a JMETER y validamos los artefactos generados. 

![alt text](S4_10.png)

        9. Analice los artefactos generados por el script recorder. 

        10. Modifique el numero de usuario en la la opcion de Thread Group. Re-ejecute los casos de prueba realizando click en la flecha verde. 

        11. Analice los resultados obtenidos en el View Results Tree y Summary Report 