# Red Hat SSO with SQL Server - Snam

This project contains a Dockerfile that is used to build an image tag for Snam's SSO image stream on OCP.

It customises its base image for use with MS SQL Server 2017 SP 1, by adding the correct JDBC drivers and configuring the Jboss application.



module add --name=com.mysql --resources=/path/to/mysql-connector-java-5.1.36-bin.jar --dependencies=javax.api,javax.transaction.api
/subsystem=datasources/jdbc-driver=mysql:add(driver-name=mysql,driver-module-name=com.mysql,driver-xa-datasource-class-name=com.mysql.jdbc.jdbc2.optional.MysqlXADataSource, driver-class-name=com.mysql.jdbc.Driver)



== Validator

org.jboss.jca.adapters.jdbc.extensions.oracle.OracleValidConnectionChecker 
org.jboss.jca.adapters.jdbc.extensions.mysql.MySQLValidConnectionChecker 



== BUILD
oc new-build --strategy docker --binary  --name sso73
oc start-build sso73  --from-dir .