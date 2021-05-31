



<img src="https://ciudadesabiertas.es/assets/img/cabiertas/logo.svg" alt="LogoCiudadesAbiertas" width="200"/> 

# DESARROLLO API REST DE DATOS REUTILIZABLE. MODELO DE TABLAS: TRÁFICO

&nbsp;

## **ÍNDICE**   
1. [AUTORES](#id1)
2. [LINKS](#id2)
3. [DIAGRAMA CONCEPTUAL](#id3)
4. [TABLAS](#id4)  
    - [TRAFICO_DISPOSITIVO_MEDICION](#id5)  
    - [TRAFICO_EQUIPO](#id6)  
    - [TRAFICO_OBSERVACION](#id7)  
    - [TRAFICO_OBSERVACION_DISP](#id8) 
    - [TRAFICO_PROPER_INTERVAL](#id9)  
    - [TRAFICO_PROPIEDAD_MEDICION](#id10) 
    - [TRAFICO_TRAMO](#id11) 
    - [TRAFICO_TRAMO_VIA](#id12)  
    - [TRAFICO_INCIDENCIA](#id13) 
5. [TAXONOMÍAS SKOS](#id14)
    - [TIPO-EQUIPO-TRAFICO](#id15)
    - [TIPO-INCIDENCIA](#id16)



&nbsp;

## AUTORES <a name="id1"></a>
- Adolfo Antón Bravo
- Edna Ruckhaus
- Hugo Lafuente Matesanz
- Leticia Rubalcaba
- Oscar Corcho
- Paola Espinoza Arias

&nbsp;

## LINKS <a name="id2"></a>


Este documento contiene la información detallada del modelo de datos asociado al vocabulario de los convenios. A continuación, se detallan los enlaces de interés asociados a este vocabulario:

- *[Documentación](http://vocab.ciudadesabiertas.es/def/transporte/trafico/index-es.html)*
- *[Repositorio](https://github.com/CiudadesAbiertas/vocab-transporte-trafico)*
- *[Webinar](https://youtu.be/takkD8AzUfw)*
- *[Requisitos](https://github.com/CiudadesAbiertas/vocab-transporte-trafico/blob/master/requirements/trafico-requisitos.xlsx)*
- *[Issues](https://github.com/CiudadesAbiertas/vocab-transporte-trafico/issues)*

&nbsp;

## DIAGRAMA CONCEPTUAL <a name="id3"></a>

Ontología de Tráfico urbano de vehículos a motor que comprende equipos de control de tráfico, dispositivos de medición de tráfico, tramos e incidencias de tráfico. La Figura 1 muestra las clases y propiedades del vocabulario de tráfico. El principal objetivo de este vocabulario es permitir la representación de los equipos de tráfico, así como de las incidencias. La Figura 2 son un diagrama del Equipo de Tráfico y del Dispositivo de Medición de Tráfico como subclase de sosa:Sensor. Por último, la Figura 3 es un diagrama de la Incidencia de Tráfico y su relación con el Tramo.

&nbsp;
![Diagrama conceptual](http://vocab.ciudadesabiertas.es/def/transporte/trafico/resources/images/vocabulario-trafico-sin-leyenda.png)
*Figura 1 - Vocabulario para la representación de datos sobre el tráfico urbano de vehículos a motor.*

&nbsp;
![Diagrama conceptual](Vocabulario-Trafico-Mediciones.png)
*Figura 2 - Diagrama del Equipo de Tráfico y del Dispositivo de Medición de Tráfico como subclase de sosa:Sensor*
&nbsp;

&nbsp;
![Diagrama conceptual](http://vocab.ciudadesabiertas.es/def/transporte/trafico/resources/images/vocabulario-trafico-incidencia.png)
*Figura 3 - Diagrama de la Incidencia de Tráfico y su relación con el Tramo*
&nbsp;



## TABLAS <a name="id4"></a>



[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 
&nbsp;
### TRAFICO_DISPOSITIVO_MEDICION <a name="id5"></a>
&nbsp;


|     Campo                  |     Tipo             |     Ejemplo                                                   |     Descripción                                                                                                                                                                         |     URL                                                                           |
|----------------------------|----------------------|---------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
|     ikey                   |     VARCHAR(50)      |     TRAFDISMED01                                              |     Identificador de la Tabla (PK).                                                                                                                                                     |                                                                                   |
|     id                     |     VARCHAR(50)      |     TRAFDISMED01                                              |     Identificador   del dispositivo de medición de tráfico.                                                                                                                             |     http://purl.org/dc/terms/identifier                                           |
|     description            |     VARCHAR(4000)    |     C. GRAN   VIA;San Bernardo-Garcia Molinas;San Bernardo    |     Una   descripción del dispositivo de medición.                                                                                                                                      |     http://purl.org/dc/terms/description                                          |
|     num_sentidos           |     INT(4)           |     2                                                         |     Número de   sentidos de circulación.                                                                                                                                                |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#numSentidos           |
|     num_carriles           |     INT(4)           |     8                                                         |     Número de   carriles de circulación.                                                                                                                                                |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#numCarriles           |
|     urbano                 |     BIT(1)           |     1                                                         |     Esta   propiedad permite describir si el dispositivo es urbano o no.                                                                                                                |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#urbano                |
|     tipo_equipo_trafico    |     VARCHAR(200)     |     lazo-magnetico                                            |     Tipo de   equipo de tráfico, equipos de control y dispositivos de medición     URL SKOS:     http://vocab.linkeddata.es/datosabiertos/kos/transporte/trafico/tipo-equipo-trafico    |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#tipoEquipoTrafico     |
|     monitorea              |     VARCHAR(50)      |     TRAFTRAM01                                                |     Relación del   Equipo de Tráfico con el Tramo que monitorea.     FK a la tabla de TRAFICO_TRAMO                                                                                     |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#monitorea             |
|     en_servicio            |     BIT(1)           |     1                                                         |     Esta   propiedad permite conocer si el dispositivo funciona o no.                                                                                                                   |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#enServicio            |
|     frecuencia_medicion    |     VARCHAR(200)     |     5 minutos                                                 |     Esta   propiedad permite conocer la frecuencia de medición del dispositivo.                                                                                                         |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#frecuenciaMedicion    |
|     observes               |     VARCHAR(200)     |     carga                                                     |     Relación   entre un Sensor y una Propiedad Observada que es capaz de obtener   observaciones.                                                                                       |     http://www.w3.org/ns/sosa/observes                                            |
|     x_etrs89               |     DECIMAL(13,5)    |     440124.33000                                              |     Coordenada X   en metros (ETRS89)                                                                                                                                                   |     https://datos.ign.es/def/geo_core#xETRS89                                     |
|     y_etrs89               |     DECIMAL(13,5)    |     4474637.17000                                             |     Coordenada Y   en metros (ETRS89)                                                                                                                                                   |     https://datos.ign.es/def/geo_core#yETRS89                                     |





[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 
&nbsp;
### TRAFICO_EQUIPO <a name="id6"></a>
&nbsp;

|     Campo                  |     Tipo             |     Ejemplo                                                   |     Descripción                                                                                                                                                                          |     URL                                                                          |
|----------------------------|----------------------|---------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|
|     ikey                   |     VARCHAR(50)      |     TRAFEQUI01                                                |     Identificador de la Tabla (PK).                                                                                                                                                      |                                                                                  |
|     id                     |     VARCHAR(50)      |     TRAFEQUI01                                                |     Identificador   del equipo de tráfico                                                                                                                                                |     http://purl.org/dc/terms/identifier                                          |
|     description            |     VARCHAR(4000)    |     C. GRAN   VIA;San Bernardo-Garcia Molinas;San Bernardo    |     Una   descripción del equipo de tráfico.                                                                                                                                             |     http://purl.org/dc/terms/description                                         |
|     num_sentidos           |     INT(4)           |     2                                                         |     Número de   sentidos de circulación.                                                                                                                                                 |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#numSentidos          |
|     num_carriles           |     INT(4)           |     8                                                         |     Número de   carriles de circulación.                                                                                                                                                 |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#numCarriles          |
|     urbano                 |     BIT(1)           |     1                                                         |     Esta   propiedad permite describir si el dispositivo es urbano o no.                                                                                                                 |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#urbano               |
|     tipo_equipo_trafico    |     VARCHAR(200)     |     radar                                                     |     Tipo de   equipo de tráfico, equipos de control y dispositivos de medición.     URL SKOS:     http://vocab.linkeddata.es/datosabiertos/kos/transporte/trafico/tipo-equipo-trafico    |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#tipoEquipoTrafico    |
|     monitorea              |     VARCHAR(50)      |     TRAFTRAM01                                                |     Relación del   Equipo de Tráfico con el Tramo que monitorea.     FK a la tabla de TRAFICO_TRAMO                                                                                      |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#monitorea            |
|     x_etrs89               |     DECIMAL(13,5)    |     440124.33000                                              |     Coordenada X   en metros (ETRS89)                                                                                                                                                    |     https://datos.ign.es/def/geo_core#xETRS89                                    |
|     y_etrs89               |     DECIMAL(13,5)    |     4474637.17000                                             |     Coordenada Y   en metros (ETRS89)                                                                                                                                                    |     https://datos.ign.es/def/geo_core#yETRS89                                    |






[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 
&nbsp;
### TRAFICO_OBSERVACION <a name="id7"></a>
&nbsp;


|     Campo                   |     Tipo             |     Ejemplo                             |     Descripción                                                                                     |     URL                                                                 |
|-----------------------------|----------------------|-----------------------------------------|-----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
|     ikey                    |     VARCHAR(50)      |     TRAFOBS01                           |     Identificador de la Tabla (PK).                                                                 |                                                                         |
|     id                      |     VARCHAR(50)      |     TRAFOBS01                           |     Identificador   de la observación de tráfico.                                                   |     http://purl.org/dc/terms/identifier                                 |
|     observed_property       |     VARCHAR(100)     | intensidad                              | Relación que enlaza la propiedad que se observa.                                                    | http://www.w3.org/ns/sosa/observedProperty                              |
|     result_time             |     DATETIME         | 2020-04-01T12:45                        | Esta propiedad establece la fecha/hora de la observación.                                           | http://www.w3.org/ns/sosa/resultTime                                    |
|     has_simple_result       |     DECIMAL(12,2)    |     30                                  |     Esta   propiedad muestra el resultado de la observación.                                        |     http://www.w3.org/ns/sosa/hasSimpleResult                           |
|     has_feature_interest    |     VARCHAR(50)      |     TRAFTRAM01                          |     Una relación   entre una Observación y la entidad para la que se ha observado.                  |     http://www.w3.org/ns/sosa/hasFeatureOfInterest                      |
|     validada                |     BIT(1)           |     0                                   |     Esta   propiedad permite conocer si se ha producido una validación de la observación   o no.    |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#validada    |
|     phenomenon_time         |     VARCHAR(50)      |     468a5a615f32d0dbee5937f86acf58b3    |     Esta   propiedad establece el intervalo de tiempo de la observación.                            |     http://www.w3.org/ns/sosa/phenomenonTime                            |




[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 
&nbsp;
### TRAFICO_OBSERVACION_DISP <a name="id8"></a>
&nbsp;

|     Campo             |     Tipo           |     Ejemplo          |     Descripción                                                                                                                    |     URL                                       |
|-----------------------|--------------------|----------------------|------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
|     ikey              |     VARCHAR(50)    |     1                |     Identificador de la Tabla (PK).                                                                                                |                                               |
|     id                |     VARCHAR(50)    |     TRAFOBSDIPS01    |     Identificador   de la observación disponible de tráfico.                                                                       |     http://purl.org/dc/terms/identifier       |
|     id_observacion    |     VARCHAR(50)    |     TRAFOBS02        |     Observación realizada por un   Dispositivo de Medición de Tráfico.      FK a la   tabla TRAFICO_OBSERVACION                    |                                               |
|     made_by_sensor    |     VARCHAR(50)    |     TRAFDISMED01     |     Relation between an Observation and the Sensor which made the   Observation.     FK a la table TRAFICO_DISPOSITIVO_MEDICION    |     http://www.w3.org/ns/sosa/madeBySensor    |




[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 
&nbsp;
### TRAFICO_PROPER_INTERVAL <a name="id9"></a>
&nbsp;

|     Campo            |     Tipo           |     Ejemplo                             |     Descripción                                                                               |     URL                                         |
|----------------------|--------------------|-----------------------------------------|-----------------------------------------------------------------------------------------------|-------------------------------------------------|
|     ikey             |     VARCHAR(50)    |     TRAPROINT01                         |     Identificador de la Tabla (PK).                                                           |                                                 |
|     id               |     VARCHAR(50)    |     468a5a615f32d0dbee5937f86acf58b3    |     Identificador   de la propiedad del intervalo de tráfico.                                 |     http://purl.org/dc/terms/identifier         |
|     has_beginning    |     VARCHAR(50)    |     2020-03-31   23:00:00               |     Comienzo de   una entidad temporal. El timestamp del inicio de un intervalo de tiempo.    |     http://www.w3.org/2006/time#hasBeginning    |
|     has_end          |     VARCHAR(50)    |     2020-03-31   23:01:00               |     Final de una   entidad temporal. El timestamp del final de un intervalo de tiempo.        |     http://www.w3.org/2006/time#hasEnd          |





[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 
&nbsp;
### TRAFICO_PROPIEDAD_MEDICION <a name="id10"></a>
&nbsp;
|     Campo            |     Tipo             |     Ejemplo                             |     Descripción                                                                                                                            |     URL                                                                     |
|----------------------|----------------------|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
|     ikey             |     VARCHAR(50)      |     TRAPROMED01                         |     Identificador de la Tabla (PK).                                                                                                        |                                                                             |
|     id               |     VARCHAR(50)      |     carga                               |     Identificador   de la propiedad de medición.                                                                                           |     http://purl.org/dc/terms/identifier                                     |
|     description      |     VARCHAR(4000)    |     Propiedad de   medición de carga    |     Una   descripción de la propiedad de medición.                                                                                         |     http://purl.org/dc/terms/description                                    |
|     unidad_medida    |     VARCHAR(50)      |     Porcentaje                          |     Esta   propiedad permite describir la unidad de medida de con la que se mide la propiedad   del Dispositivo de Medición de Tráfico.    |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#unidadMedida    |





[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 
&nbsp;
### TRAFICO_TRAMO <a name="id11"></a>
&nbsp;

|     Campo                    |     Tipo              |     Ejemplo                                                                 |     Descripción                                                                                        |     URL                                                                                                                  |
|------------------------------|-----------------------|-----------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
|     ikey                     |     VARCHAR(50)       |     1                                                                       |     Identificador de la Tabla (PK).                                                                    |                                                                                                                          |
|     id                       |     VARCHAR(50)       |     TRAFTRAM01                                                              |     Identificador   del tramo de tráfico                                                               |     http://purl.org/dc/terms/identifier                                                                                  |
|     description              |     VARCHAR(4000)     | Calles entre el cruce de Alcalá con Gran Vía y la Plaza de la Independencia | Una descripción del tramo de tráfico.                                                                  | http://purl.org/dc/terms/description                                                                                     |
|     x_etrs89_inicio_tramo    |     DECIMAL(13,5))    |     440124.33000                                                            |     Relación del tramo con el lugar donde se inicia   el tramo en coordenadas X en metros (ETRS89).    |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#inicioTramo     https://datos.ign.es/def/geo_core#xETRS89    |
|     y_etrs89_inicio_tramo    |     DECIMAL(13,5)     |     4474637.17000                                                           |     Relación del tramo con el lugar donde se inicia   el tramo en coordenadas Y en metros (ETRS89).    |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#inicioTramo     https://datos.ign.es/def/geo_core#yETRS89    |
|     x_etrs89_fin_tramo       |     DECIMAL(13,5)     |     440124.43000                                                            |     Relación del tramo con el lugar donde finaliza el   tramo en coordenada X en metros (ETRS89).      |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#finTramo     https://datos.ign.es/def/geo_core#xETRS89       |
|     y_etrs89_fin_tramo       |     DECIMAL(13,5)     |     4474637.27000                                                           |     Relación del tramo con el lugar donde finaliza el   tramo en coordenada Y en metros (ETRS89).      |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#finTramo     https://datos.ign.es/def/geo_core#yETRS89       |




[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 
&nbsp;
### TRAFICO_TRAMO_VIA <a name="id12"></a>
&nbsp;

|     Campo                                                          |     Tipo            |     Ejemplo          |     Descripción                                                                                                                                                                                                                                                                        |     URL                                                              |                              |                                                                                              |
|--------------------------------------------------------------------|---------------------|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|------------------------------|----------------------------------------------------------------------------------------------|
|     ikey                                                           |     VARCHAR(50)     |     TRAFTRAMVIA01    |     Identificador de la Tabla (PK).                                                                                                                                                                                                                                                    |                                                                      |                              |                                                                                              |
|     id                                                             |     VARCHAR(50)     |     TRAFTRAMVIA01    |     Identificador   del tramo de la vía.                                                                                                                                                                                                                                               |     http://purl.org/dc/terms/identifier                              |                              |                                                                                              |
|     id_tramo                                                       |     VARCHAR(50)     |     TRAFTRAM01       |     Tramo   definido por un punto de inicio y fin que puede pertenecer a una o más vías.                                                                                                                                                                                               |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#Tramo    |                              |                                                                                              |
|                      id_via                                        |       id_via        |                      |     VARCHAR(50)                                                                                                                                                                                                                                                                        |     496400                                                           |     Parte del   callejero    |     http://vocab.linkeddata.es/datosabiertos/def/urbanismo-infraestructuras/callejero#Via    |
|       id_via                                                       |                     |                      |                                                                                                                                                                                                                                                                                        |                                                                      |                              |                                                                                              |
|     street_address                                                 |     VARCHAR(400)    |     CALLE MAUDES     |     La dirección   de la calle.                                                                                                                                                                                                                                                        |     http://schema.org/streetAddress                                  |                              |                                                                                              |
|     municipio_title                                                |     VARCHAR(50)     |     Madrid           |     El   identificador de un Municipio es el ente local definido en el artículo 140 de   la Constitución española y la entidad básica de la organización territorial   del Estado según el artículo 1 de la Ley 7/1985, de 2 de abril, Reguladora de   las Bases del Régimen Local.    |                                                                      |                              |                                                                                              |




[comment]: <!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!> 
&nbsp;
### TRAFICO_INCIDENCIA <a name="id13"></a>
&nbsp;

|     Campo                 |     Tipo             |     Ejemplo                                                                          |     Descripción                                                                                                                                          |     URL                                                                                                                        |
|---------------------------|----------------------|--------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
|     ikey                  |     VARCHAR(50)      |     TRAFINCI01                                                                       |     Identificador de la Tabla (PK).                                                                                                                      |                                                                                                                                |
|     id                    |     VARCHAR(50)      |     TRAFINCI01                                                                       |     Identificador   de la incidencia.                                                                                                                    |     http://purl.org/dc/terms/identifier                                                                                        |
|     description           |     VARCHAR(4000)    | Corte de calles entre el cruce de Alcalá con Gran Vía y la Plaza de la Independencia | Una descripción de la incidencia de tráfico.                                                                                                             | http://purl.org/dc/terms/description                                                                                           |
|     tipo_incidencia       |     VARCHAR(200)     | obras                                                                                | Tipo de incidencia, pueden ser planificadas o no planificadas. URL SKOS: http://vocab.linkeddata.es/datosabiertos/kos/transporte/trafico/tipo-incidencia | http://vocab.ciudadesabiertas.es/def/transporte/trafico#tipoIncidencia                                                         |
|     date_posted           |     DATETIME         |     2020-03-31T08:00:00                                                              |     La fecha y   hora de publicación de una incidencia (en formato fecha ISO 8601).                                                                      |     http://schema.org/datePosted                                                                                               |
|     num_sentidos          |     INT(4)           |     2                                                                                |     Número de   sentidos de circulación.                                                                                                                 |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#numSentidos                                                        |
|     num_carriles          |     INT(4)           |     8                                                                                |     Número de   carriles de circulación.                                                                                                                 |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#numCarriles                                                        |
|     es_recurrente         |     BIT(1)           |     1                                                                                |     Esta   propiedad permite describir si la incidencia es recurrente o no.                                                                              |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#esRecurrente                                                       |
|     fecha_fin_prevista    |     DATETIME         |     2020-05-03T23:59:00                                                              |     La fecha y   hora prevista de finalización de una incidencia planificada (en formato fecha   ISO 8601).                                              |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#fechaFinPrevista                                                   |
|     recurrencia           |     VARCHAR(200)     |     Excursión   juvenil                                                              |     Esta   propiedad permite describir la recurrencia.                                                                                                   |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#recurrencia                                                        |
|     incidenciaEnTramo     |     VARCHAR(50)      |     TRAFTRAM01                                                                       |     Relación de   la Incidencia con el Tramo donde se produce la misma.     FK de la   tabla TRAFICO_TRAMO                                               |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#incidenciaEnTramo                                                  |
|     x_etrs89              |     DECIMAL(13,5)    |     440124.33000                                                                     |     Relación de   la Incidencia con el Tramo donde se produce la misma en coordenadas X en   metros (ETRS89).                                            |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#incidenciaEnTramo     https://datos.ign.es/def/geo_core#xETRS89    |
|     y_etrs89              |     DECIMAL(13,5)    |     4474637.17000                                                                    |     Relación de   la Incidencia con el Tramo donde se produce la misma en coordenadas Y en   metros (ETRS89).                                            |     http://vocab.ciudadesabiertas.es/def/transporte/trafico#incidenciaEnTramo     https://datos.ign.es/def/geo_core#yETRS89    |


&nbsp;

## TAXONOMÍAS SKOS <a name="id14"></a>
&nbsp;
### TIPO-EQUIPO-TRAFICO <a name="id15"></a>
http://vocab.linkeddata.es/datosabiertos/kos/transporte/trafico/tipo-equipo-trafico
&nbsp;
Tesauro que recoge los tipos de equipo de tráfico; es decir tanto los dispositivos que permiten controlar el tráfico como los dispositivos que permiten la realización del conteo de vehículos (intensidad del tráfico) junto con la obtención del grado de ocupación de la vía.
|     Tipo                    |     Subtipo 1                               |     Subtipo 2    |     Label                                      |     Definition                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-----------------------------|---------------------------------------------|------------------|------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     dispositivo-medicion    |                                             |                  |     Dispositivo de medición                    |     Tipo de dispositivo de medición de tráfico. Estos dispositivos   realizan mediciones.                                                                                                                                                                                                                                                                                                                                                                                                            |
|                             |     detector-bluetooth                      |                  |     Bluetooth detector                         |     Un dispositivo que detecta dispositivos bluetooth instalados   en los coches                                                                                                                                                                                                                                                                                                                                                                                                                     |
|                             |     estacion-vision-artificial              |                  |     Funcionario   interino.                    |     Permite   medir los parámetros característicos del tráfico utilizando técnicas de   procesamiento digital de imágenes con un comportamiento similar al del ojo   humano. Permite realizar la detección y seguimiento de todos los vehículos   dentro de un área determinada aparte de tomar medidas localizadas en puntos   concretos. Las variables que se pueden obtener son: Intensidad circulatoria;   velocidad media; ocupación y composición del tráfico (vehículos ligeros y pesados)    |
|                             |     lazo-magnetico                          |                  |     Lazo magnético.                            |     Dispositivo que detecta los cambios que se producen en un   campo electromagnético cuando circula un vehículo (masa metálica) sobre un   punto determinado de la calzada. Registra el número total de vehículos que   pasan y pueden clasificarlos por su longitud; número de ejes y masas.                                                                                                                                                                                                      |
|                             |     magnetometro                            |                  |     Magnetómetro.                              |     Aparato que mide la inducción de un campo magnético en una   dirección determinada.                                                                                                                                                                                                                                                                                                                                                                                                              |
|                             |     tubo-neumatico                          |                  |     Tubo neumático.                            |     Detector de goma en forma de tubo cerrado que se coloca   transversalmente a la calzada. En el otro extremo el tubo termina en una   membrana metálica flexible. Cuando pasan sobre él las ruedas de los vehículos   aumenta la presión del aire en su interior; moviendo la membrana metálica que   cierra un contacto eléctrico. Este tipo de detector es muy útil en   instalaciones provisionales o de corta duración.                                                                       |
|     equipo-control          |                                             |                  |     Equipo de control.                         |     Dispositivos que permiten controlar el tráfico.                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|                             |     camara-controltrafico                   |                  |     Cámara de control de tráfico.              |     Cámara fija de control de tráfico.                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|                             |     control-acceso                          |                  |     Control de acceso.                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|                             |     estacionamiento-indebido                |                  |     Estacionamiento indebido.                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|                             |     lector-matricula                        |                  |     Lector de matrícula.                       |     Cámara de televisión que capta un   fotograma de cada uno de los vehículos que circulan por el carril que está   monitorizando al que se le aplica un OCR que permite identificar los   caracteres que componen la matrícula.                                                                                                                                                                                                                                                                    |
|                             |     panel-mensaje-variable                  |                  |     Panel de mensaje variable.                 |     Panel de mensaje variable que se   utiliza para informar al usuario de las características del tráfico en la   vía. La información mostrada engloba incidencias fortuitas (accidentes;   vehículos averiados; etc.); estado del tráfico (retenciones); tiempos de   recorrido; colas en los accesos; obras; campañas de tráfico; etc.                                                                                                                                                            |
|                             |     radar                                   |                  |     Radar.                                     |     Equipo que controla la velocidad   de los vehículos. A su vez estos podrían clasificarse de la siguiente manera:   fijo; túnel; semáforo; inicio/fin tramo; etc.                                                                                                                                                                                                                                                                                                                                 |
|                             |     regulador-semaforico-centralizado       |                  |     Regulador semafórico centralizado.         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|                             |     regulador-semaforico-no-centralizado    |                  |     Regulador semafórico no   centralizado.    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |



&nbsp;
### TIPO-INCIDENCIA <a name="id16"></a>
http://vocab.linkeddata.es/datosabiertos/kos/transporte/trafico/tipo-incidencia
&nbsp;
Tesauro que recoge los tipos de incidencia; es decir los hechos ocurridos en la ciudad tales como obras o accidentes y que afectan a la circulación de vehículos.
|     Tipo                         |     Subtipo 1             |     Subtipo 2    |     Label                         |     Definition                                                                                                                                                                                                                                                    |
|----------------------------------|---------------------------|------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     incidencia-no-planificada    |                           |                  |     Incidencia no planificada.    |     Incidencia o evento no planificado en la ciudad que afecta a   la circulación de vehículos.                                                                                                                                                                   |
|                                  |     accidente             |                  |     accidente                     |     Evento en el que uno o más vehículos pierden el control y no   se recuperan. Incluye colisiones entre vehículos u otros usuarios de la   carretera; entre vehículos y cualquier obstáculo o son el resultado de un   vehículo que se sale de la carretera.    |
|                                  |     alerta                |                  |     Alerta.                       |                                                                                                                                                                                                                                                                   |
|                                  |     climatologica         |                  |     Climatológica.                |     Incidencia ocasionada por el clima y que conlleva al corte de   la vía. Por ejemplo: inundación de paseo marítimo; lluvias excesivas; viento.                                                                                                                 |
|                                  |     congestion-trafico    |                  |     Congestión de tráfico         |     Incidencia ocasionada cuando el nivel de servicio del tráfico   es de tipo -Congestión-.'                                                                                                                                                                     |
|                                  |     contaminacion         |                  |     Contaminación.                |     Incidencia por episodio de contaminación.                                                                                                                                                                                                                     |
|                                  |     obras-urgencia        |                  |     Obras de urgencia.            |     Obras que requieren una acción de reparación urgente. Por   ejemplo: rotura de tuberías; hundimiento de calzada.                                                                                                                                              |
|     planificada                  |                           |                  |     Incidencia planificada.       |     Incidencia o evento planificado en la ciudad que afecta a la   circulación de vehículos.                                                                                                                                                                      |
|                                  |     corte-trafico         |                  |     corte-trafico                 |     Incidencia de corta duración que requiere el corte particular   de la vía. Por ejemplo: montaje de grúa; circulación de transportes   especiales.                                                                                                             |
|                                  |     evento                |                  |     Evento.                       |     Suceso importante y programado de   índole social; académico; artístico; deportivo. Ejemplo: procesiones;   cabalgatas.                                                                                                                                       |
|                                  |     obras                 |                  |     Obras.                        |     Obras en la vía pública.                                                                                                                                                                                                                                      |
|                                  |     ocupacion-via         |                  |     Ocupación vía                 |     Ocupación de la vía pública                                                                                                                                                                                                                                   |







&nbsp;


<p float="right" align="center">
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/gobEspana-logo.svg" alt="Logo Gobierno España" width="200"/>
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/red-logo.svg" alt="Logo red.es" width="150"/>
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/ciudadesInteligentes-logo.svg" alt="Logo CiudadesInteligentes" width="150"/>
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/unionEuropea-logo.svg" alt="Logo UnionEuropea" width="200"/>
</p>


<p float="right" align="center">
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/ayuntAcoruna-logo.svg" alt="Logo AyuntACoruña" width="200"/>
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/ayuntMadrid-logo.svg" alt="Logo Madrid" width="100"/>
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/ayuntSantiagoCompostela-logo.svg" alt="Logo Concello Santiago" width="200"/>
<img src="https://ciudadesabiertas.es/assets/img/cabiertas/ayuntZaragoza-logo.svg" alt="Logo Ayun.Zaragoza" width="200"/>
</p>



