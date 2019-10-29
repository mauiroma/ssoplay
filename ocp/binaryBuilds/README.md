# Red Hat SSO 

== Validator

org.jboss.jca.adapters.jdbc.extensions.oracle.OracleValidConnectionChecker 
org.jboss.jca.adapters.jdbc.extensions.mysql.MySQLValidConnectionChecker 



== BUILD
oc new-build --strategy docker --binary  --name sso73
oc start-build sso73  --from-dir .
