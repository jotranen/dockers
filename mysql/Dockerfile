##
##   Copyright (c) 2016, Jari Otranen
##   All Rights Reserved.
##
##   Licensed under the Apache License, Version 2.0 (the "License");
##   you may not use this file except in compliance with the License.
##   You may obtain a copy of the License at
##
##       http://www.apache.org/licenses/LICENSE-2.0
##
##   Unless required by applicable law or agreed to in writing, software
##   distributed under the License is distributed on an "AS IS" BASIS,
##   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
##   See the License for the specific language governing permissions and
##   limitations under the License.
##
FROM centos:latest

##
## baseline
RUN \
   yum -y update

RUN \
   yum clean all

##
## install required tools
RUN \
   yum -y install wget which telnet

##
## install mysql
WORKDIR /root
RUN yum -y install mariadb-server mariadb
RUN /usr/bin/mysql_install_db --user=mysql --ldata=/var/lib/mysql

## 
## configure mysql
COPY setup.sql /root/
RUN \
   /usr/bin/mysqld_safe --nowatch && \
   sleep 5 && \
   /usr/bin/mysql -uroot -h127.0.0.1 < /root/setup.sql && \
   /usr/bin/mysqladmin -u root shutdown

##
## expose default mysql port to host 
EXPOSE 3306

CMD ["mysqld_safe"]
