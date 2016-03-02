FROM mysql:5.6

ADD db.dump.sql /
ADD custom.cnf /etc/mysql/conf.d/

ADD setup.sh /
RUN chmod +x /setup.sh

