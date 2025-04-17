cd succubus
apt update -y;apt upgrade
apt install mariadb-server git -y
mysql_secure_installation
mysql -u root -proot -e "create database succubus;"
mysql -u root -root succubus < doodump.sql
mysql -u root -root mysql -e "grant ALL on *.* to root@'localhost' IDENTIFIED by 'root';"
ulimit -n 999999
chmod 777 main
./main
