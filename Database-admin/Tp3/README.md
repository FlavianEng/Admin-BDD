## TP3 Admin BDD
### Création du fichier [Base SQL](https://github.com/FlavianEng/Admin-BDD/blob/master/Database-admin/Tp3/base.sql). <br> Ce dernier effectue les actions suivantes.
 - Creation de la base de données
 - Création des tables
 - Donne tous les droits sur la table games
 - Donne les droits d'écriturse et de lecturse sur la table players à un nouvel utilisateur recruiter


### Exécuter le script pour les utilisateur adéquat :
- `mysql -u manager -pmanager_password`
- `mysql -u recruiter -precruiter_password`

### Ajouter trois lignes dans la table games à l'aide du fichier [Insertion SQL](https://github.com/FlavianEng/Admin-BDD/blob/master/Database-admin/Tp3/insertion.sql). <br> Ce dernier ajoute les lignes suivantes.
- `INSERT INTO teams.games  VALUES (NOW(), false, "observation");`
- `INSERT INTO teams.games  VALUES (NOW(), true, "observation");`
- `INSERT INTO teams.games  VALUES (NOW(), false, "observation");`
- `INSERT INTO teams.games  VALUES (NOW(), false, "observation");`
- `INSERT INTO teams.games  VALUES (NOW(), true, "observation");`

### L'éxecuter avec l'utilisateur adéquat 
- `mysql -u manager -pmanager_password;`
