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

RUN \
   yum -y update
RUN \
   yum clean all

##
## install basic toolset
RUN \
   yum -y install \
      sudo        \
      tar         \
      unzip       \
      nc          \
      hostname

##
## redis
RUN yum -y update; yum clean all
RUN yum -y install epel-release; yum clean all
RUN yum -y install redis; yum clean all

##
## config
RUN sed -i -e "s/daemonize no/daemonize yes/g" /etc/redis.conf
RUN sed -i -e "s/bind 127.0.0.1/bind 0.0.0.0/g" /etc/redis.conf

EXPOSE 6379

CMD redis-server /etc/redis.conf

