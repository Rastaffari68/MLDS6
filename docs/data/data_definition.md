# Definición de los datos Predicción del Factor Primario de Incidentes Aéreos — ASRS


## Origen de los datos

-Los datos provienen del **Aviation Safety Reporting System (ASRS)**, un programa confidencial y voluntario administrado por la NASA en colaboración con la FAA (Federal Aviation Administration) de los Estados Unidos. El sistema recopila reportes de incidentes aéreos enviados por pilotos, controladores de tráfico aéreo, mecánicos y demás personal de aviación.

- **Fuente oficial:** [https://asrs.arc.nasa.gov/search/database.html](https://asrs.arc.nasa.gov/search/database.html)
- **Período cubierto:** Enero de 2006 hasta la fecha de descarga
- **Forma de obtención:** Descarga manual desde el motor de búsqueda público del ASRS en formato `.csv`, aplicando los filtros de fecha de inicio `01/2006` y fecha de fin correspondiente al mes de extracción. No se requiere autenticación; el acceso es público.
- **Frecuencia de actualización:** La base de datos ASRS se actualiza mensualmente. Se recomienda re-ejecutar la descarga al inicio de cada nueva iteración del proyecto para incorporar reportes recientes.
- **Idioma:** Inglés. Los campos narrativos (Narrative, Synopsis, Callback) contienen texto libre en mayúsculas, convención estándar del sistema ASRS.
- **Confidencialidad:** Los reportes son desidentificados por la NASA antes de su publicación. No contienen nombres de personas, aerolíneas ni identificadores precisos de aeronaves.
  
## Especificación de los scripts para la carga de datos


| Script | Descripción | Lenguaje |
|--------|-------------|----------|
| `01_download_asrs.py` | Automatiza la descarga del CSV desde el portal ASRS usando `requests` y `BeautifulSoup`. Acepta parámetros de fecha inicio/fin por línea de comandos. | Python |
| `02_load_raw.py` | Lee el CSV crudo con cabecera de dos niveles (`header=[0,1]`) usando `pandas`, valida que las 125 columnas esperadas estén presentes y persiste el DataFrame como archivo `.parquet` en la ruta de datos crudos. | Python |
| `03_clean_transform.py` | Aplica todas las transformaciones y limpiezas descritas en la sección de rutas de origen. Genera el dataset procesado, listo para el modelamiento. | Python |
| `04_load_to_db.py` | Carga el dataset procesado a la base de datos de destino (PostgreSQL) usando `SQLAlchemy`. Ejecuta upsert por `ACN` para evitar duplicados en cargas incrementales. | Python |

Todos los scripts se ejecutan en orden secuencial y pueden encadenarse mediante el orquestador `pipeline.sh`:

```bash
bash pipeline.sh --start_date 200601 --end_date 202512
```
---

## Referencias a rutas o bases de datos origen y destino

- [ ] Especificar las rutas o bases de datos de origen y destino para los datos.

### Rutas de origen de datos

- [ ] Especificar la ubicación de los archivos de origen de los datos.
- [ ] Especificar la estructura de los archivos de origen de los datos.
- [ ] Describir los procedimientos de transformación y limpieza de los datos.

### Base de datos de destino

- [ ] Especificar la base de datos de destino para los datos.
- [ ] Especificar la estructura de la base de datos de destino.
- [ ] Describir los procedimientos de carga y transformación de los datos en la base de datos de destino.
