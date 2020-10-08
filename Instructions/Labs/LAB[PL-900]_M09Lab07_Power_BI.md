---
lab:
    title: 'Laboratorio: Power BI'
    module: 'M�dulo 5: Comenzar con Power BI'
---

# M�dulo 5: Comience con Power BI
## Laboratorio: Power BI

Escenario
========

Bellows College es una instituci�n educativa que tiene un campus con varios edificios. Los visitantes del campus est�n actualmente registrados en revistas en papel. La informaci�n no se recaba de manera coherente y no se pueden recopilar y analizar los datos sobre las visitas de todo el campus. 

La administraci�n del campus querr�a modernizar el sistema de registro de visitantes de los edificios cuyo acceso est� controlado por el personal de seguridad y en los que los anfitriones deban anotar con antelaci�n las visitas y dejar constancia de ellas.

A lo largo de este curso, crear� aplicaciones y realizar� la automatizaci�n para permitir que el personal de administraci�n y seguridad de Bellows College administre y controle el acceso a los edificios en el campus. 

En este laboratorio, crear� un panel de control de Power BI que visualiza datos sobre las visitas al campus.

Pasos de alto nivel del laboratorio
======================

Seguiremos los pasos a continuaci�n para dise�ar y crear el panel de control de Power BI:

-   Con�ctese al Common Data Service 
-   Transforme los datos para incluir descripciones f�ciles de usar para los registros relacionados (b�squedas)
-   Cree y publique un informe con varias visualizaciones de la informaci�n de las visitas al campus.
-   Consulta de lenguaje natural del usuario para crear visualizaciones adicionales
-   Cree una vista m�vil


## Requisitos previos

* Finalizaci�n del laboratorio 1: modelado de datos

Cuestiones que tener en cuenta antes de comenzar
-----------------------------------

-   �Qui�n es la audiencia objetivo del informe?
-   �C�mo consumir� el informe la audiencia? �Dispositivo t�pico? �Ubicaci�n?
-   �Tiene suficientes datos que visualizar?
-   �Cu�les son las caracter�sticas que puede usar para analizar datos sobre las visitas?

Ejercicio 1: Cree informes de Power BI 
===============================

**Objetivo:** En este ejercicio, crear� un informe de Power BI basado en datos de la base de datos de Common Data Service.

Tarea�1: Preparaci�n de datos
---------------------------

1.  Encuentre la URL de su organizaci�n

    * Dir�jase al Centro de administraci�n de Power�Platform en https://admin.powerplatform.com
    * En el panel de navegaci�n izquierdo, seleccione Entornos y, luego, abra el entorno de destino.
    * Haga clic con el bot�n derecho en la **URL de entorno** en el panel **Detalles** y, luego, seleccione **Copiar direcci�n de v�nculo**.
2. Si no tiene instalado Power BI Desktop, vaya a https://aka.ms/pbidesktopstore para descargar e instalar la aplicaci�n Power BI.

3. Abra Power BI Desktop, inicie sesi�n si se le solicita.

4. Seleccione **Obtener datos**.

5. Seleccione **Power Platform** en la parte izquierda y, luego, seleccione **Common Data Service** y pulse **Conectar**.

6. Pegue la URL de entorno que copi� anteriormente en el campo **URL de servidor** y pulse **Aceptar**.

7. Expanda el nodo **Entidades**, seleccione las entidades **bc_Building** y **bc_Visit**, haga clic en **Cargar**.

8. Haga clic en el icono **Modelo** de la barra de herramientas vertical izquierda.

9. Arrastre la columna **bc_buildingid** desde la tabla **bc_Building** y su�ltela en la columna **bc_building** de la tabla **bc_Visit**. Eso crear� una relaci�n entre dos entidades que Power BI podr� usar para mostrar datos relacionados.

10. Seleccione el icono **Informe** en la barra de herramientas izquierda.

11. Expanda el nodo **bc_Visits** del panel **Campos**.

12. Haga clic en ... junto a **bc_Visits** y seleccione **Nueva columna**.

13. Complete la f�rmula del siguiente modo

    ```
    Column = RELATED(bc_Building[bc_name])
    ```

    y pulse ENTRAR. Eso agregar� un nuevo campo con el nombre del edificio en los datos de las visitas.

14. Haga clic en ... al lado del campo y seleccione **Renombrar**. Escriba **Edificio** como nombre del campo.

15. Haga clic en ... al lado del campo **bc_visitid** y seleccione **Renombrar**. Escriba **Visitas** como nombre del campo.

16. Haga clic... al lado del campo **bc_scheduledstart** y seleccione **Renombrar**. Escriba **Inicio** como nombre del campo.

17. Guarde el trabajo en curso al presionar **Archivo \| Guardar** e ingresar un nombre de archivo de su elecci�n.

## Tarea�n.�2: Cree gr�ficos y visualizaciones de tiempo

1. Pulse el icono de gr�fico circular en el panel **Visualizaciones** para insertarlo.
2. Arrastre el campo **Edificio** y col�quelo en el cuadro **Leyenda**.
3. Arrastre el campo **Visitas** y col�quelo en el cuadro de destino **Valores**.
4. Cambie el tama�o del gr�fico circular utilizando los tiradores de las esquinas para que todos los componentes del gr�fico sean visibles.
5. Haga clic en **Nuevo objeto visual** en la cinta de Power BI y, luego, seleccione el gr�fico de columnas apiladas del panel **Visualizaciones**. 
6. Arrastre el campo **Visitas** y col�quelo en el cuadro de destino **Valores**.
7. Arrastre el campo **Comienzo** y col�quelo en el cuadro de destino **Eje**.
8. En el panel Visualizaciones, haga clic en **x** junto a **D�a** y **Trimestre** para dejar en el eje solo los totales de **A�o** y **Mes**.
9. Cambie el tama�o del gr�fico como quiera con los controladores de las esquinas.
10. Pruebe la interactividad del informe:
    * Seleccione varios sectores de creaci�n en el gr�fico circular y observe los cambios en el informe de tiempos.
    * Seleccione varias barras en el gr�fico de columnas de tiempo y observe los cambios en el informe circular.
    * Explore en profundidad hasta al nivel del mes usando iconos o el comando de cintas **Datos y detalles \| Expandir el siguiente nivel**.
11. Guarde el trabajo en curso al presionar **Archivo \| Guardar**.

Ejercicio n.� 2: Crear panel de control de Power BI
================================

## Tarea�1: Publicar informe de Power BI

1. Pulse el bot�n **Publicar** en la pesta�a Inicio de la cinta.

2. Seleccione **Mi espacio de trabajo** como destino, luego presione **Seleccionar**.

3. Espere hasta que se complete la publicaci�n y haga clic en **Abrir\<nombre de su informe\>.pbix en Power BI**.

## Tarea�n.�2: Crear panel de control de Power BI

1. En la p�gina web que se ha abierto en el paso anterior, haga clic en **Mi �rea de trabajo**, en la parte superior.
2. Seleccione su **informe** de la lista de elementos.
3. Seleccione **Anclar una p�gina en vivo** en el men�. Seg�n el dise�o, es posible que deba presionar ... para mostrar elementos adicionales del men�.
4. Seleccione **Nuevo tablero** en la confirmaci�n de **Anclar al tablero**.
5. Introduzca **Administraci�n del campus** como un **Nombre del tablero**, presione **Anclar elemento en vivo**.
6. Seleccione **Mi �rea de trabajo** en la parte superior y seleccione el panel **Administraci�n del campus**.
7. Pruebe la interactividad de los gr�ficos circulares y de barras que se muestran.

## Tarea�n.� 3: Agregue visualizaciones usando lenguaje natural

1. En el panel **Administraci�n del campus**, seleccione en la parte superior **Pregunte algo sobre sus datos**.
2. Introduzca **edificios por n�mero de visitas** en el �rea de preguntas y respuestas. Se mostrar� el gr�fico de barras.
3. Seleccione **Anclar visualizaci�n**.
4. Seleccione **Tablero de instrumentos existente**, seleccione el panel de **Administraci�n del campus**, presione **Anclar**.
5. Pruebe el comportamiento haciendo clic en el gr�fico para obtener detalles de las Preguntas y respuestas.
6. Haga clic en **Salir de Preguntas y respuestas**.

## Tarea�4: Crear vista de tel�fono m�vil

1. En el panel, seleccione ... \| Vista para dispositivos m�viles.
2. Reorganice los iconos como desee.
3. Hacer clic **Vista de tel�fono** en la parte superior derecha y cambie la vista a **Vista web**.
4. Seleccione **Mi �rea de trabajo** en la parte superior y seleccione su **informe**.
5. Seleccione... \| Genere c�digo QR.
6. Si tiene un dispositivo m�vil, escanee el c�digo utilizando una aplicaci�n de esc�ner QR disponible en plataformas iOS y Android. Inicie sesi�n en su cuenta si se le solicita.
7. Navegue y explore el informe en un dispositivo m�vil.

# Desaf�os

* Paneles de control e informes para incluir planos del edificio y el campus
* Informe y analice patrones y tendencias de visitas
* Visualizaci�n sobrepasada
* Streaming de Power BI para un procesamiento casi en tiempo real para un campus grande 
