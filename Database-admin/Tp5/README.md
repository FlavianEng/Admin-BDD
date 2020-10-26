#	Database Administration - TP5 - Flavian Engevin

 1. Créer le [docker-compose.yml](https://github.com/FlavianEng/Admin-BDD/blob/master/Database-admin/Tp5/DOCKER-COMPOSE.YML) comme indiqué.
 2. **Faire les cmd suivantes :**
	 - $docker-compose build
	 - $docker-compose up
	 - $docker-compose exec mysql bash
	 - /# mysql -uroot -p
	 - mysql > create database shop;
	 - mysql > use shop;
	 - mysql > create table products (id int NOT NULL AUTO_INCREMENT, name VARCHAR(255), PRIMARY KEY (id));
	 - mysql > insert into products(name) values ("Madeleine");
	 - mysql > insert into products(name) values ("Fourme d'Ambert");
	 - mysql > insert into products(name) values ("Flan");
	 - mysql > exit
	 - /# mysqldump -uroot -p Shop > /backups/shop.sql.gz
	 - /# exit
	 - $docker-compose exec maria bash
	 - /# mariadb -uroot -p
	 - mariabd > create database shop
	 - mariabd > exit
	 - /# mariadb -uroot -p shop < /backups/shop.sql.gz
	 - /# mariadb -uroot -p
	 - mariadb > use shop
	 - mariadb > show tables;
	 - mariadb > select * from products;
