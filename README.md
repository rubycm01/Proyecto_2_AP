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
1.  Contraste de tamaño: Un planeta pequeño bloquea mucha más luz en una estrella pequeña que en una grande, haciendo el tránsito más fácil de detectar, un planeta terrestre transitando una enana roja bloquea una fracción mayor de luz que si transitara una estrella tipo Sol.
2.  Cercanía de la Zona Habitable: a Zona de Habitabilidad (ZH) en estrellas frías está muy cerca de la estrella. Un planeta en la ZH de una enana roja completa su órbita en días o semanas, permitiendo observar múltiples tránsitos en poco tiempo. En una estrella como el Sol, tendríamos que esperar un año entre cada tránsito.
3.  Límites de Habitabilidad: Según los modelos de Kopparapu et al. (2013), la ZH depende fuertemente del flujo estelar y del tipo de estrella. En estrellas frías, el pico de emisión es en el infrarrojo, y debido al albedo del hielo y la dispersión Rayleigh, los planetas en estas estrellas pueden retener calor de manera más eficiente. Nuestro filtro (200K - 320K) es una aproximación al "Hábito Conservador", pero en estrellas M, el límite interior de la ZH está más cerca debido a la interacción de la radiación con la atmósfera planetaria.

#### 4. Conclusión 
El análisis de los datos demuestra que estamos viviendo en una etapa de las Enanas Rojas. Aunque el filtro aisló más de 300 candidatos rocosos y templados, la tecnología actual (como Kepler y TESS) está optimizada para detectar estos mundos en estrellas pequeñas.

