#	Database Administration - TP8 - Flavian Engevin

 1. Créer le [docker-compose.yml](https://github.com/FlavianEng/Admin-BDD/blob/master/Database-admin/Tp8/DOCKER-COMPOSE.YML) comme indiqué.
 2. Faire les cmd suivantes :
	 - $docker-compose up
	 - $docker-compose exec mysql bash
	 - /# mysql -uroot -p
	 - mysql > create database myDb;
	 - mysql > use myDb;
	 - mysql > create table bobbyFamily (firstname VARCHAR(255), lastname VARCHAR(255));
	 - mysql > insert into bobbyFamily values ("bobo", "lebricolo"), ("bobette", "labricolette"), ("bobby", "lebricoli');
3. Aller sur son navigateur à l'adresse de promotheus : [localhost:9090](localhost:9090)
4. Cliquer dans la barre de navigation sur Status > Targets. Les states des targets devraient être toutes *UP*.
5. Entrer les commandes suivantes dans l'encadré au dessus du bouton *Execute*  

    `mysql_global_status_commands_total{command="select"} or mysql_global_status_commands_total{command="show_databases"}`

	Puis cliquer sur Executer. Le graph devrait s'afficher 
7. Entrer les commandes suivantes dans l'encadré au dessus du bouton *Execute* 

    `rate(mysql_global_status_commands_total{command="show_databases"}[5m]) or
    `rate(mysql_global_status_commands_total{command="show_tables"}[5m]) or
    `rate(mysql_global_status_commands_total{command="select"}[5m]) or
    `rate(mysql_global_status_commands_total{command="insert"}[5m])
