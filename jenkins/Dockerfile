from jenkins:2.32.2

# install plugins specified in https://github.com/kohsuke/jenkins/blob/master/core/src/main/resources/jenkins/install/platform-plugins.json

# install Organisation and Administration plugins
RUN /usr/local/bin/install-plugins.sh cloudbees-folder \
    && /usr/local/bin/install-plugins.sh antisamy-markup-formatter

# install Build Features plugins
RUN /usr/local/bin/install-plugins.sh build-timeout \
    && /usr/local/bin/install-plugins.sh credentials-binding \
    && /usr/local/bin/install-plugins.sh timestamper \
    && /usr/local/bin/install-plugins.sh ws-cleanup

# install Build Tools plugins
RUN /usr/local/bin/install-plugins.sh ant \
    && /usr/local/bin/install-plugins.sh gradle

# install Pipelines and Continuous Delivery plugins
RUN /usr/local/bin/install-plugins.sh workflow-aggregator:2.0 \
    && /usr/local/bin/install-plugins.sh github-organization-folder:1.6 \
    && /usr/local/bin/install-plugins.sh pipeline-stage-view:2.0

# install Source Code Management plugins
RUN /usr/local/bin/install-plugins.sh git \
    && /usr/local/bin/install-plugins.sh subversion

# install Distributed Builds plugins
RUN /usr/local/bin/install-plugins.sh ssh-slaves

# install User Management and Security plugins
RUN /usr/local/bin/install-plugins.sh matrix-auth \
    && /usr/local/bin/install-plugins.sh pam-auth \
    && /usr/local/bin/install-plugins.sh ldap

# install Notifications and Publishing plugins
RUN /usr/local/bin/install-plugins.sh email-ext \
    && /usr/local/bin/install-plugins.sh mailer

# install Maven
USER root

RUN apt-get update \
    && apt-get install -y maven \
    && apt-get clean

USER jenkins
