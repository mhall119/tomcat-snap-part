# Tomcat part for Snapcraft

Makes it easy to build a snap for a Java/J2EE webapp running on top of Apache Tomcat

## Usage:

To use this part, include the following in your snapcraft.yaml:

    apps:
      my-app:
        command: tomcat-launch
        daemon: simple
        plugs: [network-bind]
    
    parts:
      my-webapp:
        source: http://example.com/my-webapp.tar.gz
        plugin: dump
        organize:
            my.war: webapps/my.war
        after: [tomcat, tomcat-launcher]

All you need is to put your war file into the ./webapps/ directory, and the 
Tomcat part will take care of the rest, starting a daemon on port 8080 running
your app.
