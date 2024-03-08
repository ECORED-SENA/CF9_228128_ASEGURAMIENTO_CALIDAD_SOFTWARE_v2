<template lang="pug">
.curso-main-container.pb-3
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5.mb-5
    .titulo-principal.color-acento-contenido
      .titulo-principal__numero
        span 5
      h1 Consulta multitablas - DML
    .row.justify-content-center.mb-5
      .col-lg-2.col-4.mb-lg-0.mb-3: img(src='@/assets/curso/temas/59.svg', alt='')
      .col-lg-5.mb-lg-0.mb-3
        .cajon-b.color-primario.p-3.mb-5
          p.mb-0 Para explicar este tipo de ejercicios, crearemos una base de datos de empleados llamada ehr, y las tablas empleados y áreas, se relacionan así: un empleado pertenece a un área y un área puede tener varios empleados.
      .col-lg-5.col-6: img(src='@/assets/curso/temas/60.png', alt='')
    .row.justify-content-center.mb-5
      .col-lg-6.col-7.mb-lg-0.mb-3
        p.mb-5(data-aos='fade-right') Note que #[b area_id] en la tabla empleados puede ser nuleable: 
        img(src='@/assets/curso/temas/61.png', alt='')
      .col-lg-6.col-7.mb-lg-0.mb-3
        p.mb-5(data-aos='fade-right') Se insertarán los siguientes datos: 
        img(src='@/assets/curso/temas/62.png', alt='')
    .row.justify-content-center.mb-5
      .col-lg-8
        p Y los datos quedan así:  
    .row.justify-content-center.mb-5
      .col-lg-4.col-8.mb-lg-0.mb-3
        .rounded-3.p-4.mb-5(style="background-color: #ffce00")
          h4.mb-0 Empleados
        img(src='@/assets/curso/temas/63.png', alt='')
      .col-lg-4.col-8.mb-lg-0.mb-3
        .rounded-3.p-4.mb-5(style="background-color: #ffce00")
          h4.mb-0 Áreas 
        img(src='@/assets/curso/temas/64.png', alt='')
    Separador
    #t_5_2.titulo-segundo.color-acento-contenido(data-aos='fade-right')
      h2 5.2 Combinación interna (INNER JOIN) 
    p.mb-5(data-aos='fade-right') Con esta operación, cada fila en la tabla #[b empleados] es combinada (o unida) con los correspondientes de la tabla #[b áreas] que satisface la condición que se especifiquen en el predicado del #[em #[b JOIN.]] Cualquier fila de la tabla #[b empleados] o de la tabla áreas que no tenga uno correspondiente en la otra tabla (áreas) es excluido y solo aparecerán los que tengan correspondencia en la otra tabla. Este es el tipo de #[em #[b JOIN ]]más utilizado, por lo que es considerado el tipo de combinación predeterminado
    .row.justify-content-center.mb-5
      .col-lg-4.col-8.mb-lg-0.mb-3: img(src='@/assets/curso/temas/65.png', alt='')
      .col-lg-4.col-8.mb-lg-0.mb-3: img(src='@/assets/curso/temas/66.png', alt='')
    .row.justify-content-center.mb-5
      .col-lg-4.col-8.mb-lg-0.mb-3: img(src='@/assets/curso/temas/67.svg', alt='')
    .row.justify-content-center.mb-5
      .col-lg-10
        .tarjeta.p-4(style="background-color: #bae9d9 ")
          p.mb-0(data-aos='fade-right') La condición de la relación #[em #[b (a.id_area= e.area_id)]] consiste en que debe estar presente en ambas tablas el valor. Cuando el empleado tiene #[em #[b NULL]] en area_id no aparece, debido a que no puede cumplirla. Esto se representa con un Diagrama de Venn en la conjunción, porque el valor debe estar en ambas tablas. 
    .row.justify-content-center.mb-5
      .col-lg-7.mb-lg-0.mb-3 
        .p-4(style="background-color: #dcecfe ").mb-4
          .row.justify-content-center
            .col-lg-2.col-3.mb-lg-0.mb-3: img(src='@/assets/curso/temas/icon4.svg', alt='')
            .col-lg-10: p.mb-0 Existe otros tipos de consultas, las #[em #[b FULL JOIN, FULL OUTER JOIN, CROSS JOIN]],  que no se verán porque son muy poco empleadas, sin embargo, con el concepto principal se puede acceder a la documentación en la Web para comprobar su funcionamiento.  
        p A través de la siguiente imagen se representan también otros tipos de relaciones, Diagramas de Venn que  permiten visualizar resultados retornados. Se puede usar para ayudar a comprender los resultados que se deben esperar con cada variante de las sentencias JOIN. 
      .col-lg-5.mb-lg-0.mb-3: img(src='@/assets/curso/temas/68.png', alt='') 
    .row.justify-content-center.mb-5
      .col-lg-10
        .titulo-sexto.color-acento-contenido(data-aos='fade-right')
          h5 Figura 1
          span SQL 
        img(src='@/assets/curso/temas/69.svg', alt='Una imagen ilustrativa que muestra distintos tipos de operaciones JOIN en teoría de conjuntos o bases de datos, representadas mediante diagramas de Venn. Se muestran seis diagramas etiquetados de la siguiente manera:LEFT JOIN,RIGHT JOIN,FULL OUTER JOIN,LEFT JOIN EXCLUDING INNER JOIN,RIGHT JOIN EXCLUDING INNER JOIN,FULL OUTER JOIN EXCLUDING INNER JOIN,INNER JOIN.')
    Separador
    #t_5_2.titulo-segundo.color-acento-contenido(data-aos='fade-right')
      h2 5.2 Combinación externa
    p.mb-5(data-aos='fade-right') Es una variedad de composición de tablas que permite seleccionar algunas filas de una tabla aunque estas no tengan correspondencia con las filas de la otra tabla con la que se combina. 
    .fondo-t4.mn.p-5
      .row.justify-content-center.mb-5
        .col-lg-5.mb-lg-0.mb-3
          .tarjeta.color-secundario.p-5.h-100 
              .tarjeta.color-acento-contenido.p-3.d-inline-block.rounded-3.mb-4
                h4.mb-0.fst-italic LEFT JOIN
              p La sintaxis es muy similar a la anterior.  
                br
                br
                |#[b.text-color-acento-contenido SELECT * ] 
                br
                |#[b.text-color-acento-contenido FROM empleados AS e ]
                br
                |#[b.text-color-acento-contenido LEFT JOIN areas as a ON a.id_area = e.area_id ]
              p El resultado de este tipo de consulta contiene todos los registros de la tabla de la izquierda (la primera tabla que se define en el #[b FROM] en la consulta), independiente de si existe un registro correspondiente en la tabla de la derecha (la que se define en el #[b JOIN]). 
        .col-lg-5.mb-lg-0.mb-3
          .tarjeta.p-4(style="background-color: #bae9d9 ").h-100
            img(src='@/assets/curso/temas/70.svg', alt='').m-auto
            p La sentencia #[b #[em LEFT JOIN]] devuelve la pareja de todos los valores de la tabla izquierda (empleados), con los valores de la tabla de la derecha (áreas) correspondientes, si los hay, o retorna un valor nulo #[b #[em NULL] ]en los campos de la tabla derecha cuando no haya correspondencia.
      p.mb-5(data-aos='fade-right') A diferencia del resultado presentado en el ejemplo #[em #[b INNER JOIN]] donde no se mostraba el empleado cuya área no existía, en el ejemplo siguiente se presentarán los empleados con su respectiva área, y adicionalmente se presentará un empleado cuya área no existe. 
        br
        br
        |El empleado que no tiene área se encuentra en la región amarilla del diagrama de la derecha, mientras que los empleados con área están en la franja naranja, en la intersección de empleados y áreas. 
      .row.justify-content-center.mb-5
        .col-lg-7.col-8: img(src='@/assets/curso/temas/73.png', alt='')
      .row.justify-content-center.mb-5
        .col-lg-5.mb-lg-0.mb-3
          .tarjeta.color-secundario.p-5.h-100 
              .tarjeta.color-acento-contenido.p-3.d-inline-block.rounded-3.mb-4
                h4.mb-0.fst-italic RIGTH JOIN 
              p La sentencia #[em #[b RIGHT JOIN]] retorna todos los valores de la tabla derecha (áreas) con los valores de la tabla de la izquierda (empleados) correspondientes, si existen, o retorna un valor nulo #[em #[b NULL]] para los campos de la tabla izquierda cuando no haya correspondencia. 
                br
                br
                | #[b.text-color-acento-contenido SELECT * ]
                br 
                | #[b.text-color-acento-contenido FROM empleados AS e]
                br 
                | #[b.text-color-acento-contenido RIGHT JOIN areas as a ON a.id_area = e.area_id ]
        .col-lg-5.mb-lg-0.mb-3
          .tarjeta.p-4(style="background-color: #bae9d9 ").h-100
            img(src='@/assets/curso/temas/72.svg', alt='', style="max-width: 600px").m-auto
            p La sentencia #[b #[em LEFT JOIN]] devuelve la pareja de todos los valores de la tabla izquierda (empleados), con los valores de la tabla de la derecha (áreas) correspondientes, si los hay, o retorna un valor nulo #[b #[em NULL] ]en los campos de la tabla derecha cuando no haya correspondencia.
      .row.justify-content-center.mb-5
        .col-lg-8: img(src='@/assets/curso/temas/73.png', alt='', style="max-width: 600px")


</template>

<script>
export default {
  name: 'Tema3',
  data: () => ({
    // variables de vue
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

<style lang="sass"></style>
