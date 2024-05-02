# awswebsitehosting
AWS website hosting project
# AWS Services and other components/tools used in project
- EC2-Linux
- S3
- IAM
- ELB
- Elastic-ip
- VPC
- Terraform
- Docker


# Steps
1. Create AWS account
2. Create IAM account from root account
3. Sign into IAM account
4. Launch and connect ec2 instance
5. Install and configure webserver package to ec2 instance
6. Create website code
7. Copy website code to directory/Var/www/html
8. Manage storage at s3
9. Create load balancer for website servers
10. Assign elastic ip for workloads


# Architecture Diagram
# Contributor
- Sakshi Dhas


 sudo dnf update -y
    2  sudo dnf install -y httpd wget php-fpm php-mysqli php-json php php-devel
    3  sudo dnf install mariadb105-server
    4  [root@ip-172-31-25-170 ec2-user]# dnf info mariadb105
    5  Last metadata expiration check: 0:00:16 ago on Tue Feb 14 21:35:13 2023.
    6  Installed Packages
    7  Name         : mariadb105
    8  Epoch        : 3
    9  Version      : 10.5.16
   10  Release      : 1.amzn2023.0.6
   11  Architecture : x86_64
   12  Size         : 18 M
   13  Source       : mariadb105-10.5.16-1.amzn2023.0.6.src.rpm
   14  Repository   : @System
   15  From repo    : amazonlinux
   16  Summary      : A very fast and robust SQL database server
   17  URL          : http://mariadb.org
   18  License      : GPLv2 and LGPLv2
   19  Description  : MariaDB is a community developed fork from MySQL - a multi-user, multi-threaded
   20               : SQL database server. It is a client/server implementation consisting of
   21               : a server daemon (mariadbd) and many different client programs and libraries.
   22               : The base package contains the standard MariaDB/MySQL client programs and
   23               : utilities.
   24  sudo systemctl start httpd
   25  sudo systemctl enable httpd
   26  sudo systemctl is-enabled httpd
   27  sudo usermod -a -G apache ec2-user
   28  sudo chown -R ec2-user:apache /var/www
   29  sudo chmod 2775 /var/www && find /var/www -type d -exec sudo chmod 2775 {} \;
   30  find /var/www -type f -exec sudo chmod 0664 {} \;
   31  echo "<?php phpinfo(); ?>" > /var/www/html/phpinfo.php
   32  rm /var/www/html/phpinfo.php
   33  sudo systemctl start mariadb
   34  history

   
    sudo dnf update -y
    2  sudo dnf install -y httpd wget php-fpm php-mysqli php-json php php-devel
    3  sudo dnf install mariadb105-server
    4  [root@ip-172-31-25-170 ec2-user]# dnf info mariadb105
    5  Last metadata expiration check: 0:00:16 ago on Tue Feb 14 21:35:13 2023.
    6  Installed Packages
    7  Name         : mariadb105
    8  Epoch        : 3
    9  Version      : 10.5.16
   10  Release      : 1.amzn2023.0.6
   11  Architecture : x86_64
   12  Size         : 18 M
   13  Source       : mariadb105-10.5.16-1.amzn2023.0.6.src.rpm
   14  Repository   : @System
   15  From repo    : amazonlinux
   16  Summary      : A very fast and robust SQL database server
   17  URL          : http://mariadb.org
   18  License      : GPLv2 and LGPLv2
   19  Description  : MariaDB is a community developed fork from MySQL - a multi-user, multi-threaded
   20               : SQL database server. It is a client/server implementation consisting of
   21               : a server daemon (mariadbd) and many different client programs and libraries.
   22               : The base package contains the standard MariaDB/MySQL client programs and
   23               : utilities.
   24  sudo systemctl start httpd
   25  sudo systemctl enable httpd
   26  sudo systemctl is-enabled httpd
   27  sudo usermod -a -G apache ec2-user
   28  sudo chown -R ec2-user:apache /var/www
   29  sudo chmod 2775 /var/www && find /var/www -type d -exec sudo chmod 2775 {} \;
   30  find /var/www -type f -exec sudo chmod 0664 {} \;
   31  echo "<?php phpinfo(); ?>" > /var/www/html/phpinfo.php
   32  rm /var/www/html/phpinfo.php
   33  sudo systemctl start mariadb
   34  history
   35  exit
   36  sudo systemctl start mariadb
   37  sudo mysql_secure_installation
   38  sudo -i passwd
   39  sudo mysql_secure_installation
   40  cd /var/www/html
   41  ls
   42  sudo yum install git
   43  git --version
   44  git clone https://github.com/sakidhas/awswebsitehosting.git
   45  ls
   46  cd
   47  history



   
