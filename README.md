# omicas_G4
Proyecto Final
## Autores:Victor Cevallos, Andres Cuenca, Paola Gusqui
# TEMA: ENSAMBLE DEL GENOMA USANDO DATOS DE SECUENCIACIÓN DE PACBIO DE LA ESPECIE DE HONGO *Mucor mucedo*
## Objetivo General:  
ENSAMBLAR UN GENOMA USANDO DATOS DE SECUENCIACIÓN DE PACBIO DE LA ESPECIE DE HONGO *Mucor mucedo*
### Objetivos específicos: 
*	Realizar procedimientos de alineación y ensamblaje utilizando las plataformas web y herramientas para el efecto.
*	Identificar variaciones genéticas.
*	Caracterizar e identificar regiones complejas del genoma.
* Validar la calidad de la secuenciación final de la especie en cuestión a partir del análisis comparativo de los bancos de datos de PacBio.

## Introducción 
Para el desarrollo del tutorial escogido, se procedió a ensamblar un genoma de una especie de hongo de la familia Mucoraceae, Mucor mucedo, a partir del banco de datos de secuenciación de PacBio, que es un secuenciador que utiliza lecturas largas de genes. Estos datos se obtuvieron de la plataforma web NCBI (National Center for Biotechnology Information) por sus siglas en inglés, donde se extrajo las siguientes secuencias, SRR8534473 , SRR8534474 y SRR8534475 (NCBI., 2024). Se analizará la calidad del conjunto obtenido, en particular comparándolo con un conjunto de referencia, obtenido con el ensamblador Falcon y disponible en el sitio web de JGI.


## PACBIO 
PACBIO es un método de secuenciación masiva en tiempo real RT-Time sequencing, el cual produce secuencias largas (reads >25 kb), a diferencia de Ilumina que produce secuencias cortas (reads <0.6 kb). (Rhoads, A., & Au, K. F.; 2015).
En metodología de secuenciación por PACBIO, se fragmenta el ADN en cadenas dsDNA, las cuales se coloca adaptadores semicirculares en los extremos de las cadenas a las cuales llamamos Smrt bell (Single Molecule Real Time) por sus siglas en inglés (McEwen, J. G., & Gómez, O. M.; 2023).
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/ea786a6b-23c8-45b6-84bd-cf6a6fe470d3)
Al smrt bell se adiciona una DNA polimerasa y un primer, para iniciar la síntesis de ADN. La síntesis del ADN se realiza con nucleótidos fluorescentes. La incorporación de cada nucleótido a la cadena bicatenaria de ADN, emite una luz el cual es detectada y graficada. 
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/c6a6e5c1-e341-4326-9bcb-2c326c90e78f)

## Procedimiento 
### Obtención de los datos
*	Usaremos datos de secuenciación de lecturas largas, descargadas de las website de Zenodo y JGI
### Descarga de los genomas para ensamblaje de Zenodo
1. Cargamos la database a la plataforma Galaxy desde la página zenodo.org; concerniente a los tres archivos para el análisis. 
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/dd1316cf-177c-4863-8c3f-5a4a3c07fe17)
3. Empleando la plataforma web Galaxy, luego del análisis verificamos que la información contenida de los archivos están en formato FASTQ.
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/b7798411-7967-4e7b-8a4d-a658184c92af)

### Descarga del genoma de referencia de JGI website.
1. Ingresamos al website JGI, con la finalidad de buscar y proceder a descargar el archivo del genoma de referencia.
   ![image](https://github.com/Andreseins/omicas_G4/assets/163220753/b23c9437-e0e8-4afb-aeaa-23a6ac515283)
2. Una vez identificado el archivo de interés, procedemos a descargarlo *Mucmuc1_AssemblyScaffolds.fasta*
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/8676cf2b-cdac-4689-a363-1747894269ca)
3. Se procede a descargar el archivo.
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/7584d75f-5281-460a-83b5-caa3a836e0a9)
4. Luego de haber sido descargado el archivo, se verifica que el mismo sea tipo FASTA.
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/14128776-4ec4-498d-bdba-9cb524742a5d)

### Ensamble del genoma con Flye.
**Flye**  es un software diseñado para ensamblar secuencias genómicas a partir de datos de secuenciación masiva. Para lecturas de secuenciación de moléculas individuales, como las producidas por secuenciadores como PacBio y Oxford Nanopore. Flye también tiene un modo especial para el ensamblaje del metagenoma, lo que implica que este software puede procesar datos genómicos complejos como resultado de comunidades microbianas mixtas. (Freire B., 2021)
1. Ensamblamos una secuenciación única a partir de las 3 secuencias fastaq (SRR8534475, SRR8534474, SRR8534473) descargadas previamente.
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/2c6764b6-b60b-46f3-b752-13d319da05fe)

3. Se obtiene 4 archivos de secuenciación única, a partir del ensamblaje de las 3 secuencias previas.
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/15ffe01b-124a-4137-9a35-25fa7a3d6798)

4. El primer conjunto de datos (consenso) es un archivo FASTA que contiene el ensamblaje final de contings.
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/5a4932f3-a2cf-4bdd-bda9-14f046ead2b9)

5. El segundo y tercer archivo proporciona el gráfico del ensamblaje de contings estructurados.
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/12b392db-781b-49cd-9a4d-a7f17291fbc0)
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/08360f08-e088-4015-ad16-52cd8e46158c)

### Métricas de ensamblaje del genoma con Fasta Statistics.
FASTA statistics nos permite realizar cálculos de diferentes métricas del genoma obtenido, de secuencias de ADN o proteínas en formato FASTA, como el tamaño del ensamblaje, el número de andamios, así como el valor N50 (M. Baracochea.; 2018). Estas estadísticas nos pueden revelar información útil concerniente a la diversidad y composición de las secuencias en un conjunto de datos (autores).
1. Realizamos un análisis estadístico de nuestro genoma ensamblado.
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/5c3f4cd9-c39a-4fa3-ba20-f3f749265543)
2. Realizamos un análisis estadístico de nuestro genoma de referencia
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/5c3f4cd9-c39a-4fa3-ba20-f3f749265543)
3. Comparamos los resultados obtenidos, observando que los tanto los scaffold, contings, N50, L50, N90 son similares en ambos genomas
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/c8d8447b-0332-4f14-94d5-0521b5f593ab)
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/85a5e09a-dc9b-4e61-871d-5a4091dd48a7)

### Comparación de ensamblajes de genoma con Quast.
1.	**Quast**, es una herramienta de evaluación de calidad para ensamblajes de genómicos, opcional al fasta stadistics, es una herramienta útil, que compara diferentes ensamblajes genómicos.
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/3c75d338-e1c0-41a3-bb6e-ce5fc9f5b33d)
2.	En el gráfico inferior nos proporciona el orden de los contings (eje X) y el tamaño de los contings (eje Y).
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/0fd03d77-2267-4a50-b571-0cd771b5dddb)
3.	El gráfico inferior nos proporciona el contenido de CG, tanto del genoma ensamblado como del genoma de referencia.
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/a5a2c11f-f820-4384-bca3-91dd0e1b0297)

### Evaluación del ensamblaje del genoma con BUSCO.
Busco es una herramienta para la evaluación cuantitativa y la integridad del contenido genético esperado de un ensamblaje genómico.
1.	Resultado de la evaluación de BUSCO del genoma ensamblado.
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/41e78cfb-d487-416b-82bf-e8d6b60611c8)
2.	Resultado de la evaluación de BUSCO del genoma de referencia.
![image](https://github.com/Andreseins/omicas_G4/assets/163220753/c8ee95f3-2c7f-43dd-8abd-ccc00ca9b3fc)
3.	El análisis BUSCO confirma que estos dos ensamblajes son de calidad similar, con un número similar de genes. (El número de BUSCO C,S,D,F son similares).
### CONCLUSIONES 
1.	De la comparación de la evaluación con BUSCO, se puede corroborar que el genoma secuenciado con PacBIO es de alta calidad y ensamblado con FLYE tiene escasa diferencia con el genoma de referencia comparado.  
2.	El control de calidad realizado con FASTA STATISTICS y QUAST, nos permite verificar que la secuenciación y el ensamblaje del genoma es óptima.

### **Bibliográfica** 
* Freire, B., Ladra, S. & Parama, J.R. emory-Efficient Assembly using Flye. 
IEEE/ACM Trans. Comput. Biol. Bioinforma. 1-1 (2021).
* Rhoads, A., & Au, K. F. (2015). PacBio sequencing and its 
applications. Genomics, Proteomics and Bioinformatics, 13(5), 278-289.
* McEwen, J. G., & Gómez, O. M. (2023). Secuenciación de genomas 
utilizando lectura de cadenas largas. Revista De La Academia Colombiana De Ciencias Exactas, Físicas Y Naturales, 47(183), 439–444. https://doi.org/10.18257/raccefyn.1937.
* M. Beracochea, (2018). Bioinformática aplicada al estudio genómico de las 
cepas endófitas Kosokonia sp. UYSO10 y Rhizobium sp. UYSO24.
* NCBI (National Center for Biotechnology Information). (23 marzo de 2024) Recuperado de https://www.ncbi.nlm.nih.gov/ 
* Galaxy Project. (23 marzo de 2024). Recuperado de https://usegalaxy.org/
* OpenAI. (23 marzo de 2024). Recuperado de https://chat.openai.com 
* GibHub. (23 marzo de 2024). Recuperado de https://github.com/ 
* Zedono. (23 marzo de 2024). Recuperado de https://zenodo.org/ 
* Pb-falcon. (23 marzo de 2024). Recuperado de https://pbfalcon.readthedocs.io/en/latest/
* JGI Genome Portal. (23 marzo de 2024). Recuperado de https://genome.jgi.doe.gov/portal/
* Fenderglass-Flye. (23 marzo de 2024). Recuperado de https://github.com/fenderglass/Flye 
* Quast. (23 marzo de 2024). Recuperado de https://quast.sourceforge.net/ 
* BUSCO. (23 marzo de 2024). Recuperado de https://busco.ezlab.org/

