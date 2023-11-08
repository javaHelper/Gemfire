# Gemfire

```sh
docker run -it apachegeode/geode
Unable to find image 'apachegeode/geode:latest' locally
latest: Pulling from apachegeode/geode
530afca65e2e: Pull complete 
1c42f05880aa: Pull complete 
0d4e4a1a4532: Pull complete 
003fb093dc39: Pull complete 
1d237b73bb83: Pull complete 
Digest: sha256:28257cc79454860be47daa48853a080e2e57376fcc43f86d0b1be0291602bb7f
Status: Downloaded newer image for apachegeode/geode:latest
WARNING: The requested image's platform (linux/amd64) does not match the detected host platform (linux/arm64/v8) and no specific platform was requested
    _________________________     __
   / _____/ ______/ ______/ /____/ /
  / /  __/ /___  /_____  / _____  / 
 / /__/ / ____/  _____/ / /    / /  
/______/_/      /______/_/    /_/    1.15.1

Monitor and Manage Apache Geode
gfsh>
gfsh>help

gfsh>start locator --name=locator
Starting a Geode Locator in /locator...
..................................................
Locator in /locator on 05a1f1d86b3e[10334] as locator is currently online.
Process ID: 89
Uptime: 1 minute 13 seconds
Geode Version: 1.15.1
Java Version: 1.8.0_345
Log File: /locator/locator.log
JVM Arguments: -Dgemfire.enable-cluster-configuration=true -Dgemfire.load-cluster-configuration-from-dir=false -Dgemfire.launcher.registerSignalHandlers=true -Djava.awt.headless=true -Dsun.rmi.dgc.server.gcInterval=9223372036854775806
Class-Path: /geode/lib/geode-core-1.15.1.jar:/geode/lib/geode-server-all-1.15.1.jar

Successfully connected to: JMX Manager [host=05a1f1d86b3e, port=1099]

Cluster configuration service is up and running.


gfsh>list members
Member Count : 1

 Name   | Id
------- | ------------------------------------------------------------
locator | 05a1f1d86b3e(locator:89:locator)<ec><v0>:41000 [Coordinator]

gfsh>start server --name=server1
Starting a Geode Server in /server1...
...............
Server in /server1 on 05a1f1d86b3e[40404] as server1 is currently online.
Process ID: 279
Uptime: 19 seconds
Geode Version: 1.15.1
Java Version: 1.8.0_345
Log File: /server1/server1.log
JVM Arguments: -Dgemfire.default.locators=172.17.0.2[10334] -Dgemfire.start-dev-rest-api=false -Dgemfire.use-cluster-configuration=true -Dgemfire.launcher.registerSignalHandlers=true -Djava.awt.headless=true -Dsun.rmi.dgc.server.gcInterval=9223372036854775806
Class-Path: /geode/lib/geode-core-1.15.1.jar:/geode/lib/geode-server-all-1.15.1.jar

gfsh>create region --name=people --type=REPLICATE
Member  | Status | Message
------- | ------ | -------------------------------------
server1 | OK     | Region "/people" created on "server1"

Cluster configuration for group 'cluster' is updated.

gfsh>list regions
List of regions
---------------
people

   
gfsh>query --query="select * from /people"
Result : true
Limit  : 100
Rows   : 0

gfsh>put --key=1 --value="Prateek Ashtikar" --region=people
Result      : true
Key Class   : java.lang.String
Key         : 1
Value Class : java.lang.String
Old Value   : null

gfsh>query --query="select * from /people"
Result : true
Limit  : 100
Rows   : 1

Result
----------------
Prateek Ashtikar

gfsh>put --key=2 --value="Shrutika Ninawe" --region=people
Result      : true
Key Class   : java.lang.String
Key         : 2
Value Class : java.lang.String
Old Value   : null

gfsh>query --query="select * from /people"
Result : true
Limit  : 100
Rows   : 2

Result
----------------
Shrutika Ninawe
Prateek Ashtikar

gfsh>describe region --name="people"
Name            : people
Data Policy     : replicate
Hosting Members : server1

Non-Default Attributes Shared By Hosting Members  

 Type  |    Name     | Value
------ | ----------- | ---------------
Region | data-policy | REPLICATE
       | size        | 2
       | scope       | distributed-ack


gfsh>

```


```sh
gfsh>start server --name=server2 --server-port=0
Starting a Geode Server in /server2...
.................
Server in /server2 on 05a1f1d86b3e[36931] as server2 is currently online.
Process ID: 895
Uptime: 20 seconds
Geode Version: 1.15.1
Java Version: 1.8.0_345
Log File: /server2/server2.log
JVM Arguments: -Dgemfire.default.locators=172.17.0.2[10334] -Dgemfire.start-dev-rest-api=false -Dgemfire.use-cluster-configuration=true -Dgemfire.launcher.registerSignalHandlers=true -Djava.awt.headless=true -Dsun.rmi.dgc.server.gcInterval=9223372036854775806
Class-Path: /geode/lib/geode-core-1.15.1.jar:/geode/lib/geode-server-all-1.15.1.jar
```

```sh
gfsh>list members
Member Count : 3

 Name   | Id
------- | ------------------------------------------------------------
locator | 05a1f1d86b3e(locator:89:locator)<ec><v0>:41000 [Coordinator]
server1 | 05a1f1d86b3e(server1:279)<v1>:41001
server2 | 05a1f1d86b3e(server2:895)<v2>:41002

gfsh>
```

```sh
gfsh>describe region --name=people
Name            : people
Data Policy     : replicate
Hosting Members : server2
                  server1

Non-Default Attributes Shared By Hosting Members  

 Type  |    Name     | Value
------ | ----------- | ---------------
Region | data-policy | REPLICATE
       | size        | 2
       | scope       | distributed-ack


gfsh>
```


```sh
gfsh>stop server --name=server1
Stopping Cache Server running in /server1 on 05a1f1d86b3e[40404] as server1...
Process ID: 279
Log File: /server1/server1.log
.............................................................
gfsh>list members
Member Count : 2

 Name   | Id
------- | ------------------------------------------------------------
locator | 05a1f1d86b3e(locator:89:locator)<ec><v0>:41000 [Coordinator]
server2 | 05a1f1d86b3e(server2:895)<v2>:41002

gfsh>query --query="select * from /people"
Result : true
Limit  : 100
Rows   : 2

Result
----------------
Shrutika Ninawe
Prateek Ashtikar

gfsh>
```

```sh
gfsh>start server --name=server1
Starting a Geode Server in /server1...
.
Server in /server1 on 05a1f1d86b3e[40404] as server1 is currently online.
Process ID: 279
Uptime: 59 minutes 18 seconds
Geode Version: 1.15.1
Java Version: 1.8.0_345
Log File: /server1/server1.log
JVM Arguments: -Dgemfire.default.locators=172.17.0.2[10334] -Dgemfire.start-dev-rest-api=false -Dgemfire.use-cluster-configuration=true -Dgemfire.launcher.registerSignalHandlers=true -Djava.awt.headless=true -Dsun.rmi.dgc.server.gcInterval=9223372036854775806
Class-Path: /geode/lib/geode-core-1.15.1.jar:/geode/lib/geode-server-all-1.15.1.jar

gfsh>exit
Exiting... 

```


```sh
prateekashtikar@Prateeks-MacBook-Pro Gemfire % docker run -it apachegeode/geode
WARNING: The requested image's platform (linux/amd64) does not match the detected host platform (linux/arm64/v8) and no specific platform was requested
    _________________________     __
   / _____/ ______/ ______/ /____/ /
  / /  __/ /___  /_____  / _____  / 
 / /__/ / ____/  _____/ / /    / /  
/______/_/      /______/_/    /_/    1.15.1

Monitor and Manage Apache Geode
gfsh>
```
