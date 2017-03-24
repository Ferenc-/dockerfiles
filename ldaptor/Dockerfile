FROM clusterhq/twisted:latest

USER root
RUN apt-get update && apt-get install -y ldap-utils
RUN pip -qq install ldaptor mprpc
