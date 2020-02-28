FROM avsamit6600/python36alpine311

ENV CONTAINERNAME            "openldap"
ENV USER                     "ldap"
ENV GROUP                    "$USER"
ENV UID                      "1000"
ENV GID                      "$UID"
RUN apk add --no-cache --purge --clean-protected -u openldap-clients pwgen \
 && addgroup -g $GID $GROUP  \
 && adduser $USER -G $GROUP -u $UID -D \
 && mkdir -p /etc/openldap /var/lib/openldap /etc/ldap /var/lib/ldap \
 && chown -R $USER.$GROUP /etc/openldap /var/lib/openldap /etc/ldap /var/lib/ldap 

USER $USER 

VOLUME /etc/openldap
VOLUME /etc/ldap
VOLUME /var/lib/ldap
VOLUME /var/lib/openldap
