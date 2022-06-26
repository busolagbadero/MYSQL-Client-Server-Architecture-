Spinned up Two Ubuntu Servers (MYSQL-SERVER and MYSQL-CLIENT) on AWS.

![lulu0](https://user-images.githubusercontent.com/94229949/175835103-e96539c4-4122-4e8a-8aaa-b2e4b58d1eff.png)

SSH into  MYSQL-SERVER 

![lulu1](https://user-images.githubusercontent.com/94229949/175835242-59a4f875-6f88-4d97-9aa4-e6a2d00a3da6.png)

Updated MYSQL-SERVER  with command ' sudo apt update ' and ' sudo apt upgrade '

![lulu2](https://user-images.githubusercontent.com/94229949/175835256-addb04ec-a50f-4082-a642-60d30d230d61.png)

![lulu3](https://user-images.githubusercontent.com/94229949/175835278-9df10ba2-9c72-4e88-9750-75c76551701e.png)

Installed MYSQL-SERVER on the Ubuntu Server using ' sudo apt install mysql-server '

![lulu4](https://user-images.githubusercontent.com/94229949/175835319-3ede739a-a104-4e1c-b8bf-6db93144c8b1.png)

Then enabled mysql-server using command ' sudo systemctl enable mysql '

![lulu n](https://user-images.githubusercontent.com/94229949/175835472-cb5a6f70-baf1-4484-b904-9471966443be.png)

Created a password for MYSQL and then exited 

![lulu5](https://user-images.githubusercontent.com/94229949/175835489-56725532-a8a4-4e12-af0a-d566a3513682.png)

Created a user called ' busola ' and created a Database called ' busola_db ' on mysql-server

![lulu6](https://user-images.githubusercontent.com/94229949/175835527-9e2e8dca-c39b-473f-bc4b-54b1ab880e6b.png)

For MySQL server to allow connections from remote hosts , i VI into ' sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf ' and replace ‘ 127.0.0.1 ’ to ‘ 0.0.0.0 ’ in the bind-address

![lulu8](https://user-images.githubusercontent.com/94229949/175835651-2a7f2db8-94f2-468a-bb42-9772ed65f743.png)

For the client  to connect to MYSQL-SERVER ,i edited port 3306  inbound rule on MYSQL-SERVER security group on AWS to allow only MYSQL-CLIENT local ip address to connect to MYSQL-SERVER  

![lulua](https://user-images.githubusercontent.com/94229949/175837023-3c0821cc-ee3b-4f8d-9add-bbcf3146bbb5.png)

SSH into MYSQL-CLIENT

![lulu9](https://user-images.githubusercontent.com/94229949/175835753-890e9123-18a0-473e-83c2-774f648f0c93.png)

Updated  MYSQL-CLIENT with command ' sudo apt update ' and ' sudo apt upgrade '

![lulu10](https://user-images.githubusercontent.com/94229949/175835797-bc101c4b-d5f2-42e6-b38b-d112528ec337.png)

![lulu11](https://user-images.githubusercontent.com/94229949/175835803-44b491d8-4c47-4720-9298-ca217c409dcd.png)

Installed MYSQL-CLIENT on the Ubuntu Server using ' sudo apt install mysql-client '

![lulu12](https://user-images.githubusercontent.com/94229949/175835849-3eb02371-03bf-485e-b0f0-d97fa3124ab1.png)

To connect to MYSQL-SERVER from MYSQL-CLIENT ,I used MYSQL-SERVER's local IP address to connect from MYSQL-CLIENT. I ran  command " sudo mysql -u busola -h 172.31.92.45 -p ' . 

I was able to log in and view databases .

![lulu n-1](https://user-images.githubusercontent.com/94229949/175836011-cc56b57c-ad3c-4ab7-b49f-d1643e339f55.png)

