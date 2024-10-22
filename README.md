# Défis

## Défi 1

**Création du déploiement:**

``` kubectl create deployment defi1 -n u-8ttzx --image=xhelozs/csc8567:v1```

**Connexion sur le pod créé pour voir le port sur écoute ( le nom du pod est defi1-bc65795db-cwwd9):** 

```kubectl exec -it defi1-bc65795db-cwwd9 -n u-8ttzx -- sh ```

```
root@defi1-bc65795db-cwwd9:/# netstat -tuln
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State      
tcp        0      0 0.0.0.0:5000            0.0.0.0:*               LISTEN  

```
**Retour sur la machine hote**

**Mapping de ce port 5000 avec le port 8080 du localhost:**

``` kubectl port-forward pods/defi1-bc65795db-cwwd9 8080:5000 -n u-8ttzx ```

Navigateur : localhost:8080
