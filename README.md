# bwarrior

Pour demarrer l'application il faut :


-POSTGRES:9.5

� partir de l'image de postgree on cr�e une autre image qui va contenir la base de donn�e 

on copie init-db.sql dans le dossier docker-entrypoint-initdb.d

avec la commande  $ docker run -it --name db postgres_2:2.0 on cr�e la base de donn�e que tomcat se connectera



dans le dossier POSTGRESEXO se trouve le dockerfile de postgres





-TOMCAT:8-JRE8

� partir de l'image tomcat on cr�e une autre image en installant postgresql-9.5
 
on copie le fichier dbproject.war dans le dossier User/local/tomcat/webapps

avec la commande $ docker run -it --name tomcatdb -P --link db tomcat_2:2.0 on lie tomcat � postgres

le P permet de mapper automatiquement le port de tomcat

dans le dossier TOMCATEXO se trouve le dockerfile de tomcat

Pour acceder � l�application

tapper 

http://localhost:portdetomcat/dbproject/accueil.jsp

ou 

adresseip:portdetomcat/dbproject/accueil.jsp

dans le navigateur




