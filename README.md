### Virustotalsearches

##Scripts en python para realizar busquedas en virustotal de Ips o Urls almacenadas en un .csv##

**IP:**

En este script, leemos un archivo de excel llamado *file.xlsx* que contiene una columna llamada IP. Este a su vez contiene las direcciones IP a analizar.
Después de analizar cada dirección IP, agregamos una nueva columna llamada *Resultado* al archivo Excel y guardamos los resultados en un nuevo archivo llamado *resultados.xlsx*.

Para usar este script, simplemente coloque su archivo de Excel con las direcciones IP en la misma carpeta que el script y reemplace *'API_KEY'* con su clave de API de VirusTotal.

También asegúrese de instalar las bibliotecas pandas y openpyxl antes de ejecutar el script.
Puede hacerlo ejecutando los siguientes comandos en la línea de comandos de su sistema:

```
pip install pandas
pip install openpyxl
```

**Url:**

Para usar el script, guarda tu archivo CSV con las URLs en una carpeta junto al archivo del script y reemplaza *"TU_CLAVE_API_AQUI"* con tu clave de API de VirusTotal en la línea 5. Luego, ejecuta el script y se generará un archivo CSV llamado *"resultados.csv"* con los resultados del análisis de cada URL en VirusTotal.
