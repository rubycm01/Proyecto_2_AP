# Proyecto_2_AP

Para el desarrollo de este proyecto, el paso más importante en realción a lo aprendido de SQL y ADQL, fue la creación del TAP para la pagina de Nasa Explanets Archive, el cual esta ejecutado en los codigos que se encuentran en este repositorio, con su correspondiente archivo descargado. Este se adjunta, este README solo con fines informativos: https://exoplanetarchive.ipac.caltech.edu/TAP/sync?query=select+pl_name,discoverymethod,disc_facility,pl_rade,pl_eqt,st_teff+from+ps+where+pl_rade+is+not+null+and+pl_eqt+is+not+null&format=csv"
Teniendo en cuenta las columnas necesarias y eliminando en el mismo enlace los datos que no son nulos. 

Utilizando sql en el mismo Colab, se realizaron las consultas en relacion a la temperatura de equilibrio y el radio para generar un segundo filtro de habitabilidad, con estos datos asi se realizo la grafica que relaciona la temperatura de las estrellas con estos planetas. 

#### 1. Hallazgos del telescopio TRAPPIST-South
A través de la interfaz de la NASA, identificamos que el telescopio terrestre **TRAPPIST-South** ha descubierto un total de 7 planetas. Es importante destacar que estos corresponden al  sistema TRAPPIST-1. Este hallazgo es clave para la astronomía, ya que demuestra que estrellas muy pequeñas y frías pueden albergar sistemas planetarios múltiples y compactos con varios mundos en la zona habitable, ademas de demostrar la eficiencia de telescopios terrestres. 

#### 2. Análisis Estadístico y Sesgos de Detección
Al analizar los promedios obtenidos mediante nuestra consulta SQL, observamos diferencias significativas según el método de descubrimiento:
* Imaging (Imagen Directa): Presenta el radio promedio más alto (~19.6 radios terrestres). Esto es un sesgo esperado ya que solo podemos ver planetas gigantes y masivos que están muy lejos de su estrella.
* Transit (Tránsito):Muestra un promedio de ~6.11 radios terrestres. Es el método más eficaz para encontrar planetas pequeños, como los de la lista de "Mundos Rocosos Templados".
* Transit Timing Variations (TTV): Tiene el promedio más bajo (~3.04), siendo muy sensible para detectar planetas pequeños mediante las perturbaciones gravitatorias entre ellos.

#### 3. Análisis de la Gráfica: El predominio de las Enanas Rojas
Al observar la gráfica de Temperatura de la Estrella vs. Temperatura del Planeta, se nota un patrón: la gran mayoría de los planetas "habitables" (puntos azules) se agrupan en estrellas con temperaturas bajas, entre 2500 K y 4000 K (Enanas Rojas o tipo M). Hay muy pocos candidatos alrededor de estrellas similares al Sol (~5800 K).

Esto no significa que no existan planetas habitables en estrellas como el Sol, sino que nuestras herramientas actuales facilitan encontrar planetas en estrellas frías por tres razones:
1.  Contraste de tamaño: Un planeta pequeño bloquea mucha más luz en una estrella pequeña que en una grande, haciendo el tránsito más fácil de detectar.
2.  Cercanía de la Zona Habitable: En las estrellas frías, la zona donde el agua puede ser líquida está muy cerca de la estrella. Esto hace que los planetas tengan órbitas de pocos días, permitiendo observar muchos tránsitos en poco tiempo.
3.  Límites de Habitabilidad (Modelo de Kopparapu):Según los modelos climáticos de Kopparapu, las estrellas frías emiten más energía en el infrarrojo. Esto afecta cómo la atmósfera del planeta atrapa el calor, moviendo los límites de la zona habitable mucho más cerca de la estrella en comparación con nuestro sistema solar.

#### 4. Conclusión Final
El análisis de los datos demuestra que estamos viviendo en una etapa de las Enanas Rojas. Aunque el filtro aisló más de 300 candidatos rocosos y templados, la tecnología actual (como Kepler y TESS) está optimizada para detectar estos mundos en estrellas pequeñas.

