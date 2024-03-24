# omicas_G4
Proyecto Final
## Autores:Victor Cevallos, Andres Cuenca, Paola Gusqui
# TEMA: ENSAMBLE DEL GENOMA USANDO DATOS DE SECUENCIACIÓN DE PACBIO DE LA ESPECIE DE HONGO *Mucor mucedo*
## Objetivo General:  
ENSAMBLE DEL GENOMA USANDO DATOS DE SECUENCIACIÓN DE PACBIO DE LA ESPECIE DE HONGO *Mucor mucedo*
### Objetivos específicos: 
*	Realizar procedimientos de alineación y ensamblaje utilizando las plataformas web y herramientas para el efecto.
*	Identificar variaciones genéticas.
*	Caracterizar e identificar regiones complejas del genoma.
* Validar la calidad de la secuenciación final de la especie en cuestión a partir del análisis comparativo de los bancos de datos de PacBio.

## Introducción 
Para el desarrollo del tutorial escogido, se procedió a ensamblar un genoma de una especie de hongo de la familia Mucoraceae, Mucor mucedo, a partir del banco de datos de secuenciación de PacBio, que es un secuenciador que utiliza lecturas largas de genes. Estos datos se obtuvieron de la plataforma web NCBI (National Center for Biotechnology Information) por sus siglas en inglés, donde se extrajo las siguientes secuencias, SRR8534473 , SRR8534474 y SRR8534475 (NCBI., 2024). Se analizará la calidad del conjunto obtenido, en particular comparándolo con un conjunto de referencia, obtenido con el ensamblador Falcon y disponible en el sitio web de JGI.


## PACBIO 
PACBIO es un método de secuenciación masiva en tiempo real RT-Time sequencing, el cual produce secuencias largas de secuenciación, de esta secuenciación larga se obtiene reads de >25 kb, a diferencia de Ilumina que es un secuenciador de secuencias cortas que genera reads cortos de <0.6 kb. (Rhoads, A., & Au, K. F.; 2015).
En metodología de secuenciación por PACBIO, se fragmenta el ADN en cadenas dsDNA, las cuales se coloca adaptadores semicirculares en los extremos de las cadenas a las cuales llamamos Smrt bell (Single Molecule Real Time) por sus siglas en inglés (McEwen, J. G., & Gómez, O. M.; 2023).

Al smrt bell se adiciona una DNA polimerasa y un primer, para iniciar la síntesis de ADN. La síntesis del ADN se realiza con nucleótidos fluorescentes. La incorporación de cada nucleótido a la cadena bicatenaria de ADN, emite una luz el cual es detectada y graficada. 
## Procedimiento 
### Obtención de los datos
*	Usaremos datos de secuenciación de lecturas largas: CLR (lecturas largas continuas) de la secuenciación PacBio del genoma de la especie de hongo Mucor mucedo.
*	Adicionalmente utilizaremos más adelante un ensamblaje del genoma de referencia descargado del sitio web del JGI. Este genoma de referencia se ensambló utilizando los mismos datos de PacBio, lo usaremos como comparación con nuestro propio ensamblaje.
### Descarga de los genomas para ensamblaje de Zenodo
* 1. Para esta actividad creamos una nueva hoja de trabajo en la plataforma web Galaxy.
  2. 2.	Cargamos la database a la plataforma Galaxy desde la página zenodo.org; concerniente a los tres archivos para el análisis. 
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/dd1316cf-177c-4863-8c3f-5a4a3c07fe17)

* 1. Para esta actividad creamos una nueva hoja de trabajo en la plataforma web Galaxy.
  2. Cargamos la database a la plataforma Galaxy desde la página zenodo.org; concerniente a los tres archivos para el análisis. 
### **Bibliográfica** 
