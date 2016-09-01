
My environment:
Ubuntu 12.04, 


## 1 STEP  
#####First of all install php and composer.
Composer it is package manager, which will be using for downloading modules (like simple webserver on php)


```
sudo apt-get install curl php5-cli git   
```

```php5-cli ```- allow run php scripts from command line, curl is neccessary to install composer, git is neccessary to install php5-cli


Install composer:
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer


2.Install dependencies
php composer.phar install   //composer.phar - file, which can pull packages according to the compose.json

If any problems with installation of dependencies - try to check version of php (from terminal php -v), must be php.5.5.
In my case it was 5.3 and was obliged to make updates
sudo add-apt-repository ppa:ondrej/php5
sudo apt-get install php5

For safe case, after installation you need to chek once more the version, if it will be php.5.5 - you can continue installing dependencies. In not - trye to address for help to anyone more professional.


3. Install npm. it is requiring for install dependencies

From ubuntu 12.04 may be problems if node version is 0.6.12 (node -v //from terminal  to check version)
sudo apt-get purge nodejs npm

curl -sL https://deb.nodesource.com/setup | sudo bash -
sudo apt-get install -y nodejs

Check once more and node version must be 0.10
complete instalation of dependencies
npm install from folder where package.json is located

4.Install mysql
Run from command line
sudo apt-get install mysql-server
during instalation enter admin user name and his password
more details you can read here
http://help.ubuntu.ru/wiki/mysql

For information:
You can also install client (GUI or for terminal) to observe you database.
mysql client for terminal
sudo apt-get install mysql-client
then you can start it like  (-u prior username, which is root)
mysql -u root -p
List of available databases
mysql SHOW DATABASES; //do not forget ";" at the end of query
mysql use mysql;  //select one database, e.g. 'mysql'
mysql SELECT DATABASE(); //show name of database currently is selected
mysql SHOW TABLES; //show list of tables from currently selected database
mysql exit //exit from terminal client

To check if database is run - from terminal
netstat -at  //within list try to find localhost:mysql (mysql - means standart port or 3306)
If it is not started - run form terminal
sudo service mysql start
To stop server run
sudo service mysql stop


3. Run server
To run micro server go to src folder
cd /app/src  
and from this directory run 
php -S localhost:8080
After - input in browser localhost:8080 and JOIN!
