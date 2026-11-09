# Una aplicación Shiny para explorar y analizar agrupamientos no supervisados sin programar en R

Póster del V Congreso y XVI Jornadas de Usuarios de R (San Cristóbal de La Laguna, 25 a 27 de
noviembre de 2026).

**Abrir la aplicación:** https://aalvarogaarcia.github.io/shiny-clustering/

La aplicación corre entera en el navegador. Es una exportación de
[shinylive](https://posit-dev.github.io/r-shinylive/), que ejecuta R compilado a WebAssembly
([webR](https://docs.r-wasm.org/webr/latest/)): no hay servidor, no hay que instalar nada y el
archivo que se sube no sale del ordenador. La primera carga descarga R y los paquetes, así que
tarda más que las siguientes.

## Qué hace

Se sube una matriz de datos en CSV y se decide qué columnas entran en el agrupamiento y cuáles
solo sirven para representar el resultado (color y forma del gráfico). La reducción de
dimensionalidad se hace con PCA, t-SNE o UMAP, y el agrupamiento con k-means, DBSCAN o HDBSCAN,
siempre sobre la misma matriz y en la misma ejecución. Para cada variable de agrupamiento se
muestra su $\eta^2$ con los clusters. Cada ejecución se puede descargar como informe HTML con los
parámetros y la semilla, para repetirla.

## Ejemplo

El botón «Cargar ejemplo» carga 780 muestras (30 por población) y 500 SNPs del cromosoma 22 del
Proyecto 1000 Genomas, fase 3 (release `20130502`, GRCh37), distribuido por el International
Genome Sample Resource (IGSR) según sus [condiciones de uso](https://www.internationalgenome.org/IGSR_disclaimer).
Si se usan estos datos, IGSR pide citar
[su publicación en *Nucleic Acids Research*](https://academic.oup.com/nar/article/48/D1/D941/5580898).

## Licencia

El código de la aplicación (`app.R` y `R/`, empaquetados en `app.json`) se distribuye bajo la
GPL-3 (ver `LICENSE`). Los archivos de shinylive, webR, R y los paquetes de R de la carpeta
`shinylive/` mantienen sus propias licencias.
