# Invision-Power-Board-v5-Autotraductor
<center><img src="https://github.com/Garentti/Invision-Power-Board-v5-Autotraductor/blob/main/images/screenshot.png"></center>
## ¿Qué es y para qué sirve?
El **Autotraductor** de Invision Power Board versión 5.x.x es una herramienta automatizada utilizada para traducir automáticamente **TODA** la suite de IPS (Invision Power Suite) al idioma deseado pero en este caso por defecto al Español (España).
La herramienta es muy simple y está creada en lenguaje Python.

#### Funciones
- Conexión a base de dato MySQL.
- Extracción de los valores originales del idioma Inglés (US).
- Traducción automática mediante GoogleTranslator de deep_translator.
- Comprobación y generación automática del archivo .xml que incluye toda la traducción (si no existe).

#### Pros
1. Fácil instalación, configuración y uso.
2. Automatización total del proceso.
2. Tiempo de traducción. Lo que tarda una persona en traducir un valor, el script traduce entre 5 y 10 valores.
3. Posibilidad de reanudar la traducción si el programa se cierra (este proceso es automático al volver a ejecutar el script).
4. El script guarda el archivo .xml cada 10 traducciones completadas. Al iniciar el script este comprueba si existe el archivo *traducciones.xml* y continua la traducción.

#### Contras
1. Dependes de un servidor con Apache y MySQL. Se recomienda utilizar XAMPP o similar para agilizar el proceso mediante un servidor en localhost. También puedes hacer la conexión a un live server si ya tienes un foro IPB activo en internet pero esto alterará significativamente el uso y consumo de recursos del servidor y puede relentizar la conexión a tu web.
2. Actualmente a fecha de hoy en la versión IPB 5.0.5, hay más de 15.000 entradas por traducir por lo que el script puede llegar a tardar algunas horas.
3. Se aconseja repasar todas las traducciones desde el Admin CP de IPB una vez se haya importado el archivo .xml para verificar el sentido común de estas ya que a veces una traducción literal pierde el sentido de la expresión.

#### ¿Futuro?
Probablemente en un futuro actualice el código a una nueva versión que incluya una interfáz gráfica GUI para seleccionar en que aplicaciones deseas hacer la traducción (foro, descargas, clubs etc.) cun una barra de progreso.
>
>Nota: Si IPB obtiene cambios significativos en las versiones posteriores a esta que influyan en el actual funcionamiento, el script seguirá obteniendo mantenimiento para ejercer su función.
>

## Instalación y ejecución
1. Partiendo de la base que tienes instalados y en funcionamiento Python, XAMPP (o similar) e IPB en su versión 5.x.x (actual 5.0.5). Deberás de clonar o descargar el repositorio con todos los archivos incluidos necesarios.
2. Descomprime los archivos en una carpeta, abre la consola de comandos en la misma carpeta y escribe el siguiente comando para instalar las dependencias necesarias:
   
    ```

    pip install -r requisitos.txt

    ```
3. Una vez instaladas todas las dependencias necesarias, edita el archivo main.py para configurar la conexión con tu base de datos.
   
    ```python

    conn = mysql.connector.connect(
        host="localhost",
        user="root",
        password="",
        database="ipb"
    )

    ```

4. Si deseas también puedes cambiar el idioma de traducción en el siguiente apartado (es):
   
    ```python

    # Definir el idioma original y el de traducción
    def traducir_con_etiquetas_y_formato(texto):
      traductor = GoogleTranslator(source='en', target='es')

    ```

5. Una vez completes los pasos anteriores, puedes ejecutar el script mediante IDLE de Python o lo puedes compilar. El script comprobará si existe el archivo *traducciones.txt* y si no lo generará.
