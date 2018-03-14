Auteur: COUNIL Laurent  
Encodage: UTF-8  
Fins de ligne: UNIX (LF)

Petit projet montrant comment obtenir une fausse API, la configurer et la consommer sous angular 2.  
Dans cet exemple on récupère les configurations depuis le fichier test.json.

Pour que les serveur réponde en premier lieu il faut lancer la commande depuis le dossier du projet:  
./startFakeApi.sh  
Ce petit script va supprimer le test.json courant et le remplacer par celui présent dans src/assets puis lancer le serveur qui va renvoyer les requêtes en local.
On procède ainsi afin que chaque instance du serveur soit indépendante, les données ajoutées par post lorsque le serveur est lancé seront perdues a moins que l'on copie le test.json courant et mette à jour le fichier référence (src/assets). Le test.json courant est d'ailleurs non versionné (contrairement au fichier référence).

Ensuite vous pouvez lancer les commandes suivantes depuis un navigateur pour vérifier si tout marche:
- Page d'acceuil pour être sur que tout marche et vérifier l'ensemble des endpoints disponibles  
http://localhost:3000/
- Renvoie l'ensemble des données disponibles dans tous les endpoints  
http://localhost:3000/db
- renvoie toutes les données data  
http://localhost:3000/data
- renvoie les données data ayant un id = 3  
http://localhost:3000/data/3
- renvoie les données data ayant un nom qui est test  
http://localhost:3000/data?name=test
- renvoie les 10 premières données data ayant un nom qui est test (1 page = 10 résultats par défaut)  
http://localhost:3000/data?name=test&_page=1
- renvoie données data 6 à 10 ayant un nom qui est test  
http://localhost:3000/data?name=test&_page=2&_limit=5
- renvoie tous les items ayant un item nommé object qui contient une propriété nom  
http://localhost:3000/data?object.name=second%20object
- un autre endpoint d'api avec des données différentes
http://localhost:3000/secondEndpoint
