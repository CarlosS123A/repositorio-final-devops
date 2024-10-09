Proyecto: Despliegue en Kubernetes con Jenkins
Dentro del repositorio encontrarás todos los archivos correspondientes al reto, tanto pipelines como
archivos YAML, configuraciones en la Cloud Shell, documentos y diagrama solicitado, entre otros
archivos importantes y código fuente de las aplicaciones backend y frontend.
Instrucciones para Autenticar con el Archivo JSON
Este documento proporciona los pasos para autenticarte y configurar el acceso a un clúster de
Kubernetes en Google Cloud usando un archivo JSON de una cuenta de servicio. Sigue estos
pasos para configurar tu entorno correctamente.
Pasos para Autenticar con el Archivo JSON
1. Descargar el Archivo JSON:
 - Descarga el archivo JSON que se compartió y guárdalo en una ubicación segura en tu máquina
local (por ejemplo, en 'C:\Users\TuUsuario\Documents\k8s-auditor-key.json').
2. Instalar Google Cloud SDK y kubectl (si no están instalados):
 - Descarga e instala el SDK de Google Cloud desde https://cloud.google.com/sdk/docs/install.
 - Asegúrate de que 'kubectl' esté instalado para interactuar con Kubernetes (viene con el SDK de
Google Cloud).
3. Autenticarte Usando el Archivo JSON:
 - Abre una terminal (CMD, PowerShell, o terminal en Linux/Mac) y ejecuta el siguiente comando:
 gcloud auth activate-service-account --key-file="ruta/a/tu/archivo.json"
 - Reemplaza 'ruta/a/tu/archivo.json' con la ruta exacta al archivo JSON que descargaste.
4. Configurar el Acceso al Clúster de Kubernetes:
 - Usa el siguiente comando para obtener las credenciales del clúster y configurar 'kubectl':
 gcloud container clusters get-credentials jenkins-cluster --zone us-central1 --project
YOUR_PROJECT_ID
 - Reemplaza 'jenkins-cluster' con el nombre del clúster.
 - Reemplaza 'us-central1' con la zona del clúster.
 - Reemplaza 'YOUR_PROJECT_ID' con el ID de tu proyecto en Google Cloud.
5. Verificar el Acceso al Clúster:
 - Una vez configurado, puedes ejecutar:
 kubectl get pods --all-namespaces
 - Esto te permitirá ver todos los pods y confirmar que tienes acceso al clúster.

   ![image](https://github.com/user-attachments/assets/4a65eb22-d68a-47c4-b809-5ec406fcbb87)


   ![image](https://github.com/user-attachments/assets/3cd872b9-6d24-44d8-91b2-9a604b4c3082)

