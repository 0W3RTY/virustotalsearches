### Virustotalsearches

Script en python para realizar busquedas en virustotal de Ips en bulk almacenadas en un .csv

**IP:**

En este script, leemos un archivo de excel llamado *file.xlsx* que contiene una columna llamada IP. Este a su vez contiene las direcciones IP a analizar.

Al ejecutar el script después de analizar cada dirección IP, este agrega dos nuevas columna una llamada *Positives* que nos dice si la deteccion es positiva o no.

Y otra llamada *Score* que nos da el conteo de todas las detecciones de antivirus sobre las ips agregadas. Finalmente nos guarda los resultados en un nuevo archivo llamado *resultados.xlsx*.

Para usar este script, simplemente coloque su archivo de Excel con las direcciones IP en la misma carpeta que el script y reemplace en el script *'API_KEY'* con su clave de API de VirusTotal.

También asegúrese de instalar las bibliotecas pandas y openpyxl antes de ejecutar el script.
Puede hacerlo ejecutando los siguientes comandos en la línea de comandos de su sistema:

```
pip install pandas
pip install openpyxl
```
