Typically individual DML (Insert, Update, Delete) statements are performed in an autocommit transaction, 
which those commands are committed as soon as the statement successfully completes. 
There will be no opportunity to roll back the database to the state prior to the statement if autocommit is enabled. 
When something goes wrong, the only restoration option available is to reconstruct the data from a backup (providing one exists).

In MySQL, autocommit is on by default for InnoDB, here in this case, we are going to teach you how to disable this option.

1.First, we want to setup a enviroment first:
Pulliing the MySQL image and running it on a docker container

 `docker run -d --name mysql -e MYSQL_ROOT_PASSWORD=root mysql:latest`{{execute}} 
 
 Please be noted that time is required for setting up the container, you should wait for at least 20s before proceed to the next step

2.Run the MySQL container in Interactive Mode to get access of the bash shell of the container

 `docker exec -it mysql bash`{{execute}} 

3.Now we can login into our mySQL database with user ROOT

 `mysql -u root -p`{{execute}} 

4.Last, enter password that you set above

 `root`{{execute}}  
 
 
 You should see the MySQL prompt after following these steps
 and login into MySQL with Root user.
 
 Now, we will move on if you finished double checking...