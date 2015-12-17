#!/bin/bash

# Download and place binary in JBoss. WAR_FILE_URL variable is specified as an environment variable in the BuildConfig
curl -o $JBOSS_HOME/standalone/deployments/ROOT.war -O ${WAR_FILE_URL}

# Call default assemble script
/usr/local/sti/assemble
