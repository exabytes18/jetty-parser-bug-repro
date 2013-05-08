Either run directly with mvn:
    mvn clean compile jetty:run

Or compile WAR and run with standalone jetty:
    mvn clean package
    cp target/ROOT.war $JETTY_HOME/webapps
    $JETTY_HOME/bin/jetty.sh start

Send a malformed request:
    echo -e "GET / HTTP/1.1\r\nHost: 127.0.0.1:8080\r\nAccept-Language:\r\n\r\n" | nc 127.0.0.1 8080
