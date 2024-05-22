<template lang="pug">
.curso-main-container.pb-3
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5.mb-5
    .titulo-principal.color-acento-contenido
      .titulo-principal__numero
        span 4
      h1 SQL para consulta de datos - DML 
    .p-4(style="background-color: #bae9d9")
      .row.justify-content-center.align-items-center
        .col-lg-3.col-6: img(src='@/assets/curso/temas/27.png', alt='' style="z-index: 1").position-relative
        .col-lg-9
          .bg-white.p-4(style="margin-left: -3rem; z-index: -1")
            p.mb-0.ms-4 Para encontrar la información dentro de una base de datos, es preciso escudriñar dentro de la estructura de los datos su estructura y su naturaleza, por ejemplo, el tipo de datos fecha tiene una estructura YYYY-MM-DD,  y si necesito listar los registros de un año determinado, se necesita una función que refiera a ese dato particular dentro de la columna; por este motivo, es necesario revisar algunas funciones antes de empezar a trabajar consultas de datos. 
    Separador
    #t_4_1.titulo-segundo.color-acento-contenido(data-aos='fade-right')
      h2 4.1 Funciones en MySQL
    p.mb-5(data-aos='fade-right') Dado que MySQL cuenta con una amplia gama de operadores y ofrece un extenso repertorio de funciones, se dispone de numerosas opciones para el manejo de datos. Sin embargo, para facilitar la comprensión de su funcionamiento general, solo se explicarán algunas funciones esenciales.
      br
      br
      | #[b A continuación, se listan algunas de las más usadas:]
    .row.justify-content-center.mb-5
      .col-lg-10
        .titulo-sexto.color-acento-contenido(data-aos='fade-right')
          h5 Tabla 1. 
          span Algunas funciones de MySQL 
        .tabla-a.color-acento-botones.mb-5
          table
            thead.border-top-0
              tr(style="background-color: #ffce00 ")
                th Función
                th Descripción
            tbody
              tr
                td LENGTH 
                td Devuelve la longitud de una cadena (en bytes).
              tr
                td SUM  
                td Calcula la suma de un conjunto de valores. 
              tr
                td MAX 
                td Devuelve el valor máximo en un conjunto de valores. 
              tr
                td MIN 
                td Devuelve el valor mínimo en un conjunto de valores. 
              tr
                td CEIL 
                td Redondea el valor entero más pequeño que es mayor o igual que un número. 
              tr
                td COUNT 
                td Devuelve el número de registros devueltos por una consulta de selección. 

              tr
                td AVG 
                td Devuelve el valor medio de una expresión.
              tr
                td YEAR  
                td Devuelve la parte del año para una fecha determinada.
              tr
                td MONTH 
                td Devuelve la parte del mes para una fecha determinada.
              tr
                td DAY 
                td Devuelve el día del mes para una fecha determinada.
              tr
                td DATE 
                td Extrae la parte de la fecha de una expresión de fecha y hora.
              tr
                td TIME 
                td Extrae la parte de tiempo de una hora / fecha y hora determinadas.
              tr
                td SEC_TO_TIME 
                td Devuelve un valor de tiempo basado en los segundos especificados.
                
    p.mb-5(data-aos='fade-right') Para este ejemplo se usará una base de datos de llamadas telefónicas, esta base de datos tiene la estructura que se verá a continuación y con ella se aprenderá a hacer consultas. 
      br  
      br  
      | #[b Ejemplo llamadas telefónicas]              
    .bg-img-1.bg-full.mb-5(data-aos="zoom-in")
      .bg-container-full
        .tarjeta.tarjeta--bgSlyde.p-4(data-aos="fade-left")
          SlyderA(tipo="b")
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Descargue el archivo para crear la base de datos #[strong "cdr"] (recuerde que debe descomprimirlo) y de él extraiga el archivo cdr.sql. Este archivo crea una base de datos llamada #[strong "cdr"] y dentro una tabla con el mismo nombre. 
                  br
                  br
                  |Importe el archivo con la sentencia source < ruta del archivo sql >. 
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/28.png', alt='')            
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Conozca los datos de prueba con los que se trabajará. 
                a.boton.color-acento-botones.indicador__container(@click="modal1 = true")
                  span(style="color: #12263F ") Ampliar Tabla
                  .indicador--click(v-if="mostrarIndicador")
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/29.png', alt='')            
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p A partir de este punto usaremos #[b.text-color-acento-contenido #[b MySQL Workbench]] para visualizar mejor los resultados. 
                ol.lista-ol
                  li.d-flex.mb-0
                    span.text-bold(style="color: #ffce00") 1. 
                    p.mb-0  Haga clic en la pestaña de uso de bases de datos. 
                  li.d-flex.mb-0
                    span.text-bold(style="color: #ffce00") 2. 
                    p.mb-0  Cree una nueva conexión. 
                  li.d-flex.mb-0
                    span.text-bold(style="color: #ffce00") 3. 
                    p.mb-0  Póngale el nombre que prefiera a esa conexión. 
                  li.d-flex.mb-0
                    span.text-bold(style="color: #ffce00") 4. 
                    p.mb-0  Ponga el usuario root. 
                  li.d-flex.mb-0
                    span.text-bold(style="color: #ffce00") 5. 
                    p.mb-0  Digite el nombre de la base de datos que usará: #[strong "cdr"]. 
                  li.d-flex.mb-0
                    span.text-bold(style="color: #ffce00") 6. 
                    p.mb-0  Haga clic en ok. 
              .col-lg-7.mb-4.mb-md-0
                img(src='@/assets/curso/temas/30b.png', alt='')            
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Ahora debe conectar dando doble clic.
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/31b.png', alt='')   
        
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p  Ya se dispone de bases de datos y se sabe cómo agregar y cambiar datos. A continuación se aprenderá a extraer datos de una base de datos. Para ello se volverá a utilizar la sentencia #[b.text-color-acento-contenido #[em SELECT]]. 
                  br
                  br
                  |La sintaxis de #[b.text-color-acento-contenido #[em SELECT]] es complicada, Sin embargo, en este punto no se explicará todas sus opciones. Una manera más general reside en la siguiente sintaxis: 
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/34.png', alt='')            
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Para listar todos los elementos de la tabla se debe usar la sentencia:  #[b.text-color-acento-contenido #[em SELECT * FROM cdr]]
                  br
                  br
                  |Escriba la sentencia anterior. Al decir *  estamos diciendo que seleccione todas las columnas de la tabla #[b cdr]: 
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/35b.png', alt='')            
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p También se pueden seleccionar solo algunas, para esto, se deben separar por una coma, así:  
                  br
                  br
                  | #[b.text-color-acento-contenido #[em SELECT origen, destino, duracion FROM cdr ]]
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/36b.png', alt='')            
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Cabe mencionar que es posible asignar un alias a cualquiera de las expresiones #[b.text-color-acento-contenido #[em SELECT]] y se puede realizar empleando la palabra AS ,aunque esta palabra es opcional: 
                  br
                  br
                  | #[b.text-color-acento-contenido #[em SELECT origen AS num_orig, destino, duracion AS tiempo_llamada FROM cdr]] 


              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/37b.png', alt='')            
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Suponga que se necesita saber cuánto cobrar por las llamadas salientes realizadas a celular o larga distancia nacional (que el destino tenga 10 dígitos), sabiendo que el valor del minuto son $85 (ochenta y cinco pesos): 
                  br
                  br
                  |Lo primero que se necesita tener en cuenta, es que hay que filtrar las llamadas que tienen un destino de 10 dígitos. Esto se logra con la función #[b.text-color-acento-contenido #[em LENGTH]] y el número de segundos que tiene la llamada desde que es atendida, se guarda en la columna facturar. Pero para saber cuántos minutos duró la llamada, se debe  dividir el número de segundos por 60 y eso nos da el número de minutos. Ahora, el número de minutos no es entero y tiene datos decimales, se debe redondear hacia arriba con la función #[b.text-color-acento-contenido #[em CEIL]] y este valor ya redondeado, se puede multiplicar por 85 que es el valor del minuto. 




              .col-lg-5.mb-4.mb-md-0
                  figure 
                    img(src='@/assets/curso/temas/38b.png', alt='')            
         
                
    ModalA(:abrir-modal.sync="modal1")
      .tabla-a.color-acento-botones.mb-5
        table
          thead.border-top-0(style="background-color: #ffce00")
            tr
              th(colspan="4") Diccionario de datos
          tbody
            tr
              td Tabla
              td(colspan="3") CDR  (Call Data Records
            tr
              td Fecha
              td(colspan="3") DD/MM/YYY
            tr
              td Propósito 
              td(colspan="3") Guarda el registro de llamadas entrantes y salientes de un sistema de telefonía PBX. 
            tr.fw-bold(style="background-color: #dddddd")
              td Campo 
              td Tipo 
              td Longitud 
              td Descripción 
            tr
              td Propósito 
              td DATETIME 
              td 0 
              td Fecha y hora de registro de la llamada.
            tr
              td Origen 
              td VARCHAR 
              td 80
              td Número de teléfono o extensión del llamante. 
            tr
              td Destino
              td VARCHAR 
              td 80
              td Número de teléfono o extensión del llamado o destino.
            tr
              td Estado
              td VARCHAR 
              td 30
              td ANSWERED, BUSY, FAILED, NO ANSWER, que representa lo que sucede finalmente con la llamada. 
            tr
              td Duración 
              td INT 
              td 10
              td Lo que dura la llamada incluyendo el tiempo de timbrado. 
            tr
              td Facturar 
              td INT 
              td 10
              td Lo que dura la llamada desde el momento en que es contestada la llamada. 
    Separador
    #t_4_2.titulo-segundo.color-acento-contenido(data-aos='fade-right')
      h2 4.2 Operadores    
    p.mb-5(data-aos='fade-right') SQL tiene muchos operadores diferentes según el tipo de columna. Esos operadores se emplean para construir expresiones que se usan en las consultas.
    .fondo-t4.mn.p-5.mb-4
      .row.justify-content-center.align-items-center.mb-5
        .col-lg-6.mb-lg-0.mb-3
          .tarjeta.color-secundario.p-5 
            img(src='@/assets/curso/temas/41.svg', alt='' style="width: 86px").mb-4   
            .tarjeta.color-acento-contenido.p-3.d-inline-block.rounded-3.mb-4
              h4.mb-0 a ) Operadores lógicos  
            p Los operadores lógicos se emplean para crear expresiones lógicas complejas. Permite el uso de álgebra booleana y ayuda a crear condiciones o filtros de información mucho más precisos. 
              br
              br
              |Recuerde que en el álgebra booleana o álgebra de bool, existen dos valores posibles para ser operados y son los resultados: verdadero y falso. MySQL dispone de dos constantes para esos valores: #[b.text-color-acento-contenido #[em TRUE y FALSE]], respectivamente. 
              br
              br
              |En SQL se añade un tercer valor. Esto es para hacer posible trabajar con valores #[b.text-color-acento-contenido #[em NULL]]. El valor verdadero se implementa como 1 o #[b.text-color-acento-contenido #[em TRUE]], el falso como 0 o #[b.text-color-acento-contenido #[em FALSE]] y el desconocido como #[b.text-color-acento-contenido #[em NULL]]. 
        .col-lg-6.mb-lg-0.mb-3
          .tarjeta.p-4(style="background-color: #bae9d9").mb-4
            p.mb-0 Se ejecuta la siguiente sentencia en la consulta para que mirar la naturaleza de los datos. 
          img(src='@/assets/curso/temas/42.png', alt='') 
      p.mb-5(data-aos='fade-right').fw-bold Conozcamos algunos operadores:
      TabsB.color-acento-contenido.mb-5
        .py-4.py-md-5.p-5(titulo="Operador AND" :icono="require('@/assets/curso/temas/icon.svg')")
          p.mb-5(data-aos='fade-right') En SQL se puede usar el operador #[em #[b AND]], que se trata de un operador binario, es decir, requiere de dos operandos. El resultado de la operación es verdadero, solo si ambos operandos son verdaderos, falso si cualquier operando es falso o nulo si alguno de los dos es nulo.  
            br
            br
            |#[b Esto se representa mediante la siguiente tabla de verdad:] 
          .row
            .col-md-6.mb-4.mb-md-0
              .tabla-a.color-acento-botones.mb-5
                table.fw-bold
                  caption Nota. Tomado de MySQL AND Operator By Examples, 2020.
                  thead.border-top-0
                    tr(style="background-color: #ffce00 ")
                      th A
                      th B
                      th C
                      
                      
                  tbody
                    tr
                      td FALSO
                      td FALSO
                      td FALSO
                    tr
                      td FALSO
                      td VERDADERO
                      td FALSO
                    tr
                      td VERDADERO
                      td FALSO
                      td FALSO
                    tr
                      td VERDADERO
                      td VERDADERO
                      td VERDADERO
                    tr
                      td FALSO
                      td.fst-italic NULL
                      td FALSO
                    tr
                      td.fst-italic NULL
                      td FALSO 
                      td FALSO
                    tr
                      td VERDADERO
                      td.fst-italic NULL
                      td.fst-italic NULL
                    tr
                      td.fst-italic NULL
                      td VERDADERO
                      td.fst-italic NULL
                      
                      
            .col-md-6 
              img(src='@/assets/curso/temas/43.png', alt='')
        .py-4.py-md-5.p-5(titulo="Operador OR" :icono="require('@/assets/curso/temas/icon.svg')")
          p.mb-5(data-aos='fade-right') El operador OR también es binario. Si ambos operandos siendo diferentes de #[b #[em NULL]] y el resultado es verdadero si alguno de ellos es verdadero y falso si los dos son falsos. Si uno de los operandos es #[b #[em NULL]] el resultado es verdadero si el otro es verdadero y #[b #[em NULL]] si el otro es falso.  
            br
            br
            |La tabla de verdad es: 
          .row
            .col-lg-6.mb-4.mb-md-0
              .tabla-a.color-acento-botones.mb-5
                table.fw-bold
                  caption Nota. Tomado de MySQL AND Operator By Examples, 2020.
                  thead.border-top-0
                    tr(style="background-color: #ffce00 ")
                      th A
                      th B
                      th A OR B
                      
                      
                  tbody
                    tr
                      td FALSO
                      td FALSO
                      td FALSO
                    tr
                      td FALSO
                      td VERDADERO
                      td VERDADERO
                    tr
                      td VERDADERO
                      td FALSO
                      td VERDADERO
                    tr
                      td VERDADERO
                      td VERDADERO
                      td VERDADERO
                    tr
                      td FALSO
                      td.fst-italic NULL
                      td.fst-italic NULL
                      
                    tr
                      td.fst-italic NULL
                      td FALSO 
                      td.fst-italic NULL
                    tr
                      td VERDADERO
                      td.fst-italic NULL
                      td VERDADERO
                    tr
                      td.fst-italic NULL
                      td VERDADERO
                      td VERDADERO
                      
                      
            .col-md-6 
              img(src='@/assets/curso/temas/44.png', alt='')
      .row.justify-content-center.align-items-center.mb-5
        .col-lg-6.mb-lg-0.mb-3
          .tarjeta.color-secundario.p-5 
            img(src='@/assets/curso/temas/41.svg', alt='' style="width: 86px").mb-4   
            .tarjeta.color-acento-contenido.p-3.d-inline-block.rounded-3.mb-4
              h4.mb-0 b ) Operadores de igualdad   
            p El operador igual (=) compara dos expresiones y da como resultado TRUE si son iguales o FALSE si son diferentes. Ya lo hemos usado en ejemplos anteriormente 
              br
              br
              | #[b.text-color-acento-contenido #[em SELECT * FROM cdr  WHERE registro = ‘2018-01-02 10:19:08’ ]]
        .col-lg-6.col-8.mb-lg-0.mb-3: img(src='@/assets/curso/temas/45.png', alt='')
      .row.justify-content-center.align-items-center.mb-5
        .col-lg-6.mb-lg-0.mb-3
          .tarjeta.color-secundario.p-5 
            img(src='@/assets/curso/temas/41.svg', alt='' style="width: 86px").mb-4   
            .tarjeta.color-acento-contenido.p-3.d-inline-block.rounded-3.mb-4
              h4.mb-0 c ) Operadores de desigualdad  
            .tabla-a.color-acento-botones.mb-5
              table.w-60
                thead
                  tr(style="background-color: #ffce00 ")
                    th(style="color: #12263f") Operador
                    th(style="color: #12263f ") Descripción
                tbody.bg-white
                  tr
                    td(style=" color: #12263f") <= 
                    td(style=" color: #12263f") Menor o igual 
                  tr
                    td(style=" color: #12263f") < 
                    td(style=" color: #12263f") Menor 
                  tr
                    td(style=" color: #12263f") > 
                    td(style=" color: #12263f") Mayor 
                  tr
                    td(style=" color: #12263f") >= 
                    td(style=" color: #12263f") Mayor o igual 
            p 
              b.text-color-acento-contenido SELECT * FROM cdr   
                br
                |WHERE registro >= '2018-01-02 10:19:08'  
                br
                |AND registro <= '2018-01-04 10:19:08' 
                    
                    
                    
        .col-lg-6.col-8.mb-lg-0.mb-3: img(src='@/assets/curso/temas/46b.png', alt='', style="max-width: 600px").mx-auto
    Separador
    #t_4_3.titulo-segundo.color-acento-contenido(data-aos='fade-right')
      h2 4.3 Ordenar resultados 
    p.mb-5(data-aos='fade-right') También, se puede agregar una cláusula de orden #[b #[em ORDER]] BY para lograr resultados ordenados por la columna que se quiera y se puede hacer ascendente o descendente con la cláusula #[b #[em ASC]] y #[b #[em DESC]] respectivamente. 
    .bg-img-1.bg-full.mb-5(data-aos="zoom-in")
      .bg-container-full
        .tarjeta.tarjeta--bgSlyde.p-4(data-aos="fade-left")
          SlyderA(tipo="b")
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Por ejemplo, se desean listas las llamadas en orden de duración descendente (de mayor a menor): 
                  br
                  br
                  | #[b.text-color-acento-contenido SELECT * FROM cdr ORDER BY duracion DESC ]
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/47b.png', alt='', style="max-width: 505px")             
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Y también de manera ascendente por la fecha:  
                  br
                  br
                  | #[b.text-color-acento-contenido SELECT * FROM cdr ORDER BY registro ASC]
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/48b.png', alt='', style="max-width: 500px")            
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Igualmente, se puede ordenar por el resultado de operación, aunque el rendimiento de la consulta disminuye. Ejemplo, para llamadas de larga distancia o celular a 85 pesos el minuto, que se ordene por la llamada que más costo tenga a la que menos costo tenga. 

                  br
                  br
                  | #[b.text-color-acento-contenido SELECT *, CEIL(facturar/60) * 85 AS valor] FROM cdr  
                  br
                  | #[b.text-color-acento-contenido WHERE LENGTH(destino) = 10   ]
                  br
                  | #[b.text-color-acento-contenido ORDER BY  CEIL(facturar/60) * 85  DESC ]


              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/49b.png', alt='', style="max-width: 544px")             
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Se puede agrupar por varios criterios a la vez, por ejemplo si se ordenan los resultados por la duración y si hay repetidos, que el siguiente criterio sea la fecha de registro.  
                  br
                  br
                  |#[b.text-color-acento-contenido  SELECT * FROM cdr ] 
                  br
                  |#[b.text-color-acento-contenido ORDER BY  facturar  DESC , registro  ASC ]


              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/50b.png', alt='', style="max-width: 476px")  
    Separador
    #t_4_4.titulo-segundo.color-acento-contenido(data-aos='fade-right')
      h2 4.4 Listar y limitar resultados
    p.mb-5(data-aos='fade-right') La principal forma de limitar resultados es filtrando condiciones en los datos con la cláusula #[b #[em WHERE]], sin embargo cuando a pesar de eso los datos son muchos, es necesario paginarlo o presentarlo por partes, para ello se miraría la cláusula #[b #[em LIMIT]].  
      br
      br
      | #[b Ejemplo]   
    .bg-img-1.bg-full.mb-5(data-aos="zoom-in")
      .bg-container-full
        .tarjeta.tarjeta--bgSlyde.p-4(data-aos="fade-left")
          SlyderA(tipo="b")
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Se desea filtrar las llamadas larga distancia o celular de todo el año 2016 que cuestan más de $1.000, y presentarlas ordenadas de mayor a menor por el precio.
                  br
                  br
                  | #[b.text-color-acento-contenido SELECT *, CEIL(facturar/60) * 85 AS valor]   
                  br
                  | #[b.text-color-acento-contenido OM cdr  ]
                  br
                  | #[b.text-color-acento-contenido ERE YEAR(registro) = 2016 ]
                  br
                  | #[b.text-color-acento-contenido D LENGTH(destino) = 10 ]  
                  br
                  | #[b.text-color-acento-contenido D CEIL(facturar/60) * 85 > 200 ]
                  br
                  | #[b.text-color-acento-contenido DER BY valor DESC  ]
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/51b.png', alt='', style="max-width: 479px")       
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Los datos que la consulta arroja seguramente son muchos. Para saber cuántos resultados cumplen con las condiciones de la cláusula #[b.text-color-acento-contenido #[em WHERE]], es preciso contarlos con la función #[b.text-color-acento-contenido #[em COUNT]], pero la consulta no debe usar la cláusula #[b.text-color-acento-contenido #[em ORDER]] BY porque la función #[b.text-color-acento-contenido #[em COUNT]] solamente arroja una fila y con una única columna, por lo tanto, el resultado no se puede ordenar. 
                  br
                  br
                  | #[b.text-color-acento-contenido SELECT COUNT(*) ]
                  br
                  | #[b.text-color-acento-contenido FROM cdr  ]
                  br
                  | #[b.text-color-acento-contenido WHERE YEAR(registro) = 2016 ]
                  br
                  | #[b.text-color-acento-contenido AND LENGTH(destino) = 10   ]
                  br
                  | #[b.text-color-acento-contenido AND CEIL(facturar/60) * 85 > 200 ]

 
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/52.png', alt='')        
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Como se puede ver, son muchos registros, pero si el interés es mostrar los primeros 10, utilice la cláusula #[b.text-color-acento-contenido #[em LIMIT.]] 
                  br
                  br
                  | #[b.text-color-acento-contenido SELECT *, CEIL(facturar/60) * 85 AS valor   ]
                  br
                  | #[b.text-color-acento-contenido FROM cdr  ]
                  br
                  | #[b.text-color-acento-contenido WHERE YEAR(registro) = 2016 ]
                  br
                  | #[b.text-color-acento-contenido AND LENGTH(destino) = 10  ] 
                  br
                  | #[b.text-color-acento-contenido AND CEIL(facturar/60) * 85 > 200 ]
                  br
                  | #[b.text-color-acento-contenido ORDER BY valor DESC ]
                  br
                  | #[b.text-color-acento-contenido LIMIT 10 ]


              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/53b.png', alt='', style="max-width: 453px")  
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Para lograr hacer esto, la cláusula #[b.text-color-acento-contenido #[em LIMIT]] permite dos parámetros. Cuando se utilizan los dos, el primero muestra el número de la primera fila a traer, y el segundo el número de filas a traer. Se puede por ejemplo, rescatar las filas de dos en dos: 

                  br
                  | #[b.text-color-acento-contenido  SELECT *, CEIL(facturar/60) * 85 AS valor ]  
                  br
                  | #[b.text-color-acento-contenido FROM cdr  ]
                  br
                  | #[b.text-color-acento-contenido WHERE YEAR(registro) = 2016 ]
                  br
                  | #[b.text-color-acento-contenido AND LENGTH(destino) = 10  ] 
                  br
                  | #[b.text-color-acento-contenido AND CEIL(facturar/60) * 85 > 200] 
                  br
                  | #[b.text-color-acento-contenido ORDER BY valor DESC ]
                  br
                  | #[b.text-color-acento-contenido LIMIT 10, 10 ]
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/54b.png', alt='', style="max-width: 428px")          
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Y con la siguiente consulta se traen los próximos 10. 
                  br
                  br
                  | #[b.text-color-acento-contenido SELECT *, CEIL(facturar/60) * 85 AS valor   ]
                  br
                  | #[b.text-color-acento-contenido FROM cdr ] 
                  br
                  | #[b.text-color-acento-contenido WHERE YEAR(registro) = 2016 ]
                  br
                  | #[b.text-color-acento-contenido AND LENGTH(destino) = 10   ]
                  br
                  | #[b.text-color-acento-contenido AND CEIL(facturar/60) * 85 > 200 ]
                  br
                  | #[b.text-color-acento-contenido ORDER BY valor DESC ]
                  br
                  | #[b.text-color-acento-contenido LIMIT 20, 10 ]
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/55b.png', alt='', style="max-width: 433px")  
    Separador
    #t_4_5.titulo-segundo.color-acento-contenido(data-aos='fade-right')
      h2 4.5 Agrupar filas 
    p Se pueden agrupar filas en la salida con la sentencia #[b #[em SELECT]], según los valores de una columna, usando la cláusula #[b #[em GROUP BY.]] Y se usa con funciones de agrupación como lo son, #[b #[em AVG, SUM, MAX, COUNT,]] entre otros. 
      br
      br
      | #[b Ejemplo]
    .bg-img-1.bg-full.mb-5(data-aos="zoom-in")
      .bg-container-full
        .tarjeta.tarjeta--bgSlyde.p-4(data-aos="fade-left")
          SlyderA(tipo="b")
            .row.justify-content-center.align-items-center.p-2
              .col-lg-8.col-md-auto
                p Se desea saber cuántas llamadas entrantes se realizaron durante cada uno de los meses del año 2017. Las llamadas entrantes son aquellas que no provienen de una extensión local, es decir, el origen tiene más de tres dígitos. 
                  br
                  br
                  | #[b.text-color-acento-contenido SELECT MONTH(registro) AS mes, COUNT(*) AS cantidad ]
                  br
                  | #[b.text-color-acento-contenido FROM cdr  ]
                  br
                  | #[b.text-color-acento-contenido WHERE LENGTH(origen) > 3 AND YEAR(registro) = 2017 ]
                  br
                  | #[b.text-color-acento-contenido GROUP BY mes ]  
                  
            .row.justify-content-center.align-items-center.p-2
              .col-lg-8.col-md-auto
                p Pero si se desea mostrar también la agrupación de los años 2017, 2018 y 2019 y los meses de cada uno de estos años, sería:  
                  br
                  br
                  | #[b.text-color-acento-contenido SELECT YEAR(registro) AS año,  MONTH(registro) AS mes, COUNT(*) AS cantidad ]
                  br
                  | #[b.text-color-acento-contenido FROM cdr  ]
                  br
                  | #[b.text-color-acento-contenido WHERE LENGTH(origen) > 3 AND YEAR(registro) IN (2017,2018,2019) ]
                  br
                  | #[b.text-color-acento-contenido GROUP BY año, mes ]
                  br
                  | #[b.text-color-acento-contenido ORDER BY año, mes  ]


                  
            .row.justify-content-center.align-items-center.p-2
              .col-lg-8.col-md-auto
                p Es de resaltar que para agregar más de una opción en el año, se usó la cláusula IN y se ordena por año y como segundo criterio por mes. 
                  br
                  br
                  | #[b.text-color-acento-contenido SELECT YEAR(registro) AS año,  MONTH(registro) AS mes, COUNT(*) AS cantidad ]
                  br
                  | #[b.text-color-acento-contenido FROM cdr  ]
                  br
                  | #[b.text-color-acento-contenido WHERE LENGTH(origen) > 3 AND YEAR(registro) IN (2017,2018,2019) ]
                  br
                  | #[b.text-color-acento-contenido GROUP BY año, mes ]
                  br
                  | #[b.text-color-acento-contenido ORDER BY año, mes ] 


                  




</template>

<script>
export default {
  name: 'Tema5',
  data: () => ({
    mostrarIndicador: true,
    modal1: false,
  }),
  mounted() {
    this.$nextTick(() => {
      this.$aosRefresh()
    })
  },
  updated() {
    this.$aosRefresh()
  },
}
</script>

<style lang="sass">
.text-black
  tr, th, td
  color: #12263f !important
</style>
