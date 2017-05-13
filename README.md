## Configuration and script files for Gremlin server and JanusGraph
### Supports gremlin server configs for both websockets and REST  

Subdirectores are based on your JanusGraph base install directory.  These files assumes a base directory of /opt/janusgraph-0.1.1-hadoop2  

I'm using the currently available janusgraph-0.1.1-hadoop2 distro available from [JanusGraph](https://github.com/JanusGraph/janusgraph/releases) with a mixin from information I got from the [TINKERPOP-(980)])(https://github.com/apache/tinkerpop/pull/439) issue.  The latest gremlin-server.sh discussed there can be found [here](https://raw.githubusercontent.com/apache/tinkerpop/master/gremlin-server/src/main/bin/gremlin-server.sh)  

Create the janusgraph-rest.service and janusgraph-websoc.service in /etc/systemd/system, ensuring that the ExecStart, ExecStop an PIDFile parameters point to the apropriate directories on your system.  It's pretty important to use the full path names where they are used in these files, Janusgraph and Gremlin server doesn't play well in some cases.  

Type the following at the command promt:  

`sudo systemctl enable janusgraph-rest`  

`sudo systemctl enable janusgraph-websoc`  

`sudo systemctl start janusgraph-rest`  

`sudo systemctl start janusgraph-websoc`
