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
            my.jar: webapps/my.jar
        after: [tomcat]
