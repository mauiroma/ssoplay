FROM docker-registry.default.svc:5000/openshift/redhat-sso73-openshift
#FROM registry.access.redhat.com/redhat-sso-7/sso73-openshift

MAINTAINER <name> <name@.com>

ENV DEFAULT_LAUNCH $JBOSS_HOME/bin/openshift-launch.sh

COPY extensions/postconfigure.sh    $JBOSS_HOME/extensions/
COPY extensions/actions.cli         $JBOSS_HOME/extensions/
COPY extensions/*.jar               $JBOSS_HOME/extensions/

USER root
RUN chmod 774 $JBOSS_HOME/extensions/*.sh
USER jboss

CMD $DEFAULT_LAUNCH





