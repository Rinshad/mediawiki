# mediawiki
Mediawiki docker file and helm chart

# Pre-requisites 

1. Kubernetes cluster
2. Helm 
3. kubectl

Tools version which I used \ 
kubernetes v1.24.9 \
helm v3.8.0 \
docker 20.10.12 

# How to run 

```
helm install medaiwiki ./mediawiki-chart -n app-namespace
helm install mariadb ./mariadb-chart -n app-namespace
```

The application will start listinging on the port 80 after the deployment. Use the loadblancer public IP address to access the application from a browser. To setup the application database use the database details provided in the chart. Last download the LocalSettings.php file and it can be placed inside the apache document root (/var/www/html) with the help of configmap mount.
