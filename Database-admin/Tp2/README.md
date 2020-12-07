## TP2 Admin BDD
### Création de la base de donées events :
- `CREATE DATABASE events; USE events;`

### Ajout d'une table public_events :
- `CREATE TABLE public_events (event_date DATE, event_name VARCHAR(50), event_age_requirement TINYINT);`
- `CREATE TABLE private_events (event_date DATE, event_name VARCHAR(50), event_age_requirement TINYINT);`

### Création d'un utilisateur event_manager :
- `GRANT ALL PRIVILEGES ON events TO 'event_manager'@'localhost' IDENTIFIED BY 'password';`
  
### Création un utilisateur event_supervisor :
- `GRANT ALL PRIVILEGES ON events.public_events TO 'event_supervisor'@'localhost' IDENTIFIED BY 'password';`
### Validation des droits :
**Ne pas oublier, sinon les droits ne seront pas appliqué.**
- `FLUSH PRIVILEGES;` 

### Connexion à l'utilisateur event_manager :
- `mysql -u event_manager -ppassword`

#### Insertion des 3 lignes de données dans les tables :
On commence par la table public_events
- `INSERT INTO public_events VALUES (NOW(), 'Bob', '38');`
- `INSERT INTO public_events VALUES (NOW(), 'Bobby', '11');`
- `INSERT INTO public_events VALUES (NOW(), 'Bobette', '93');`
On recommence dans la table private_events
- `INSERT INTO private_events VALUES (NOW(), 'Bob', '38');`
- `INSERT INTO private_events VALUES (NOW(), 'Bobby', '11');`
- `INSERT INTO private_events VALUES (NOW(), Bobette', '93');
`
### Connexion à l'utilisateur event_supervisor :
- `mysql -u event_supervisor -ppassword`

#### Vérification du contenu de la table public_events :
- `USE events;`
- `SELECT * FROM public_events;`
- *Affichage des resultats de la table pulic_events*
On essaie ensuite (cela doit échouer) : 
- `SELECT * FROM private_events;`
L'erreur devrait être :
- *command denied to user 'event_supervisor'@'localhost' for table 'private_events'*

### Reconnexion en utilisateur ROOT :
- `mysql -u root -pmypassword`

#### Suppression de l'utilisateur event_supervisor :
- `DROP USER 'event_supervisor'@'localhost';`
- `FLUSH PRIVILEGES;`