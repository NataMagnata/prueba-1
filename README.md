# Proyecto de Análisis de Energía Solar

Este proyecto contiene una serie de notebooks de Jupyter para analizar el potencial de energía solar y su viabilidad económica en diferentes ubicaciones. El análisis incluye tanto sistemas Fotovoltaicos (PV) como de Energía Solar Concentrada (CSP).

## Estructura del Proyecto

El proyecto consta de los siguientes notebooks:

1. `final_limpiezas.ipynb`: Limpieza y procesamiento de datos
   - Procesa datos meteorológicos de archivos CSV
   - Convierte datos al formato PVWatts v8
   - Maneja múltiples ubicaciones (Chile, Rusia, China)
   - Calcula estadísticas de irradiación solar

2. `final_simulacion_pv.ipynb`: Simulación de sistema fotovoltaico
   - Simula el rendimiento del sistema PV
   - Analiza la producción de energía

3. `final_simulacion_csp.ipynb`: Simulación de Energía Solar Concentrada
   - Simula el rendimiento del sistema CSP
   - Analiza la producción de energía térmica

4. `final_lcoe.ipynb`: Análisis del Costo Nivelado de Energía
   - Calcula el LCOE para diferentes escenarios
   - Análisis de viabilidad económica

5. `final_analisis_sensibilidad.ipynb`: Análisis de sensibilidad
   - Analiza cómo diferentes parámetros afectan el rendimiento del sistema
   - Evalúa la sensibilidad económica

## Requisitos

- Python 3.10 o superior
- Jupyter Notebook
- Paquetes de Python requeridos:
  - pandas
  - numpy
  - matplotlib
  - pvlib (para simulaciones PV)
  - SAM (System Advisor Model) para simulaciones CSP

## Instalación

1. Clonar este repositorio:
```bash
git clone [url-del-repositorio]
cd [nombre-del-repositorio]
```

2. Crear un entorno virtual (recomendado):
```bash
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
```

3. Instalar los paquetes requeridos:
```bash
pip install -r requirements.txt
```

## Uso

1. Iniciar Jupyter Notebook:
```bash
jupyter notebook
```

2. Abrir los notebooks en el siguiente orden:
   - Primero ejecutar `final_limpiezas.ipynb` para procesar los datos meteorológicos
   - Luego ejecutar `final_simulacion_pv.ipynb` o `final_simulacion_csp.ipynb` según sus necesidades
   - Finalmente, ejecutar `final_lcoe.ipynb` y `final_analisis_sensibilidad.ipynb` para el análisis económico

## Datos de Entrada

El proyecto utiliza datos meteorológicos en formato CSV con la siguiente convención de nombres:
- `tmy_[latitud]_[longitud]_[año_inicio]_[año_fin].csv`

Ejemplo: `tmy_-38.320_-71.960_2005_2023.csv`

Los datos de entrada deben contener las siguientes columnas:
- time(UTC) (Tiempo UTC)
- T2m (Temperatura)
- RH (Humedad Relativa)
- G(h) (Irradiancia Global Horizontal)
- Gb(n) (Irradiancia Normal Directa)
- Gd(h) (Irradiancia Horizontal Difusa)
- WS10m (Velocidad del Viento)
- WD10m (Dirección del Viento)
- SP (Presión Superficial)

## Salida

Los datos procesados se guardarán en formato PVWatts v8 con la siguiente convención de nombres:
- `[nombre_archivo_original]_pvwatts_final.csv`


