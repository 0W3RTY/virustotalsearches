### Virustotalsearches

##Scripts en python para realizar busquedas en virustotal de Ips o Urls almacenadas en un .csv

**IP:**

En este script, leemos un archivo de Excel llamado file.xlsx que contiene una columna llamada IP este a su vez contiene las direcciones IP a analizar.
Después de analizar cada dirección IP, agregamos una nueva columna llamada Resultado al archivo Excel y guardamos los resultados en un nuevo archivo llamado resultados.xlsx.

Para usar este script, simplemente coloque su archivo de Excel con las direcciones IP en la misma carpeta que el script y reemplace 'API_KEY' con su clave de API de VirusTotal.

También asegúrese de instalar las bibliotecas pandas y openpyxl antes de ejecutar el script.
Puede hacerlo ejecutando los siguientes comandos en la línea de comandos de su sistema:

```
pip install pandas
pip install openpyxl
```
