# Gemfire

```
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
alter async-event-queue (Not Available)
    alter attributes of async-event-queue, needs rolling restart for new attributes to take effect. 
alter disk-store (Available)
    Alter some options for a region or remove a region in an offline disk store.
alter gateway-sender (Not Available)
    Alter some options for the Gateway Sender on a member or members.
alter query-service (Not Available)
    Alter configuration parameters for the query service
alter region (Not Available)
    Alter a region with the given path and configuration.
alter runtime (Not Available)
    Alter a subset of member or members configuration properties while running.
backup disk-store (Not Available)
    Perform a backup on all members with persistent data. The target directory must exist on all members, but can be either local or shared.
    This command can safely be executed on active members and is strongly recommended over copying files via operating system commands.
change loglevel (Not Available)
    This command changes log-level run time on specified servers.
clear defined indexes (Not Available)
    Clears all the defined indexes.
close durable-client (Not Available)
    Attempts to close the durable client, the client must be disconnected.
close durable-cq (Not Available)
    Closes the durable cq registered by the durable client and drains events held for the durable cq from the subscription queue.
compact disk-store (Not Available)
    Compact a disk store on all members with that disk store. This command uses the compaction threshold that each member has configured for
    its disk stores. The disk store must have "allow-force-compaction" set to true.
compact offline-disk-store (Available)
    Compact an offline disk store. If the disk store is large, additional memory may need to be allocated to the process using the
    --J=-Xmx??? parameter.
configure pdx (Not Available)
    Configures Geode's Portable Data eXchange for all the cache(s) in the cluster. This command would not take effect on the running members
    in the system.
     This command persists the pdx configuration in the locator with cluster configuration service. 
     This command should be issued before starting any data members.
connect (Available)
    Connect to a jmx-manager either directly or via a Locator. If connecting via a Locator, and a jmx-manager doesn't already exist, the
    Locator will start one.
create async-event-queue (Not Available)
    Create Async Event Queue.
create data-source (Not Available)
    (Experimental) Creates a JDBC data source and verifies connectivity to an external JDBC database.
create defined indexes (Not Available)
    Creates all the defined indexes.
create disk-store (Not Available)
    Create a disk store.
create gateway-receiver (Not Available)
    Create the Gateway Receiver on a member or members.
create gateway-sender (Not Available)
    Create the Gateway Sender on a member or members.
create index (Not Available)
    Create an index that can be used when executing queries.
create jdbc-mapping (Not Available)
    (Experimental) Create a JDBC mapping for a region for use with a JDBC database.
create jndi-binding (Not Available)
    Create a jndi binding that holds the configuration for the XA datasource.
create lucene index (Not Available)
    Create a lucene index that can be used to execute queries.
create region (Not Available)
    Create a region with the given path and configuration. Specifying a --key-constraint and --value-constraint makes object type
    information available during querying and indexing.
debug (Available)
    Enable/Disable debugging output in GFSH.
define index (Not Available)
    Define an index that can be used when executing queries.
deploy (Not Available)
    Deploy JARs to a member or members.  Only one of either --jar or --dir may be specified.
deregister driver (Available)
    (Experimental) Deregister a driver with the cluster's Driver Manager using the name of a driver class contained within a currenly
    deployed jar.
describe client (Not Available)
    Display details of specified client
describe config (Not Available)
    Display configuration details of a member or members.
describe connection (Available)
    Display information about the current connection.
describe data-source (Not Available)
    (Experimental) Describe the configuration of the given data source.
describe disk-store (Not Available)
    Display information about a member's disk store.
describe jdbc-mapping (Not Available)
    (Experimental) Describe the specified JDBC mapping
describe jndi-binding (Not Available)
    Describe the configuration of the given jndi binding.
describe lucene index (Not Available)
    Display the description of lucene indexes created for all members.
describe member (Not Available)
    Display information about a member, including name, id, groups, regions, etc.
describe offline-disk-store (Available)
    Display information about an offline disk store.
describe query-service (Not Available)
    Describes the clusters query service
describe region (Not Available)
    Display the attributes and key information of a region.
destroy async-event-queue (Not Available)
    destroy an Async Event Queue
destroy data-source (Not Available)
    Destroy a data source that holds a jdbc configuration.
destroy disk-store (Not Available)
    Destroy a disk store, including deleting all files on disk used by the disk store. Data for closed regions previously using the disk
    store will be lost.
destroy function (Not Available)
    Destroy/Unregister a function. The default is for the function to be unregistered from all members.
destroy gateway-receiver (Not Available)
    Destroy the Gateway Receiver on a member or members.
destroy gateway-sender (Not Available)
    Destroy the Gateway Sender on a member or members.
destroy index (Not Available)
    Destroy/Remove the specified index.
destroy jdbc-mapping (Not Available)
    (Experimental) Destroy the specified JDBC mapping.
destroy jndi-binding (Not Available)
    Destroy a JNDI binding that holds the configuration for an XA datasource.
destroy lucene index (Not Available)
    Destroy the lucene index.
destroy region (Not Available)
    Destroy/Remove a region.
disconnect (Available)
    Close the current connection, if one is open.
echo (Available)
    Echo the given text which may include system and user variables.
execute function (Not Available)
    Execute the function with the specified ID. By default will execute on all members.
exit (Available)
    Exit GFSH and return control back to the calling process.
export cluster-configuration (Not Available)
    Exports the cluster configuration artifacts as a zip file.
export config (Not Available)
    Export configuration properties for a member or members.
export data (Not Available)
    Export user data from a region to a file.
export logs (Not Available)
    Export the log files for a member or members.
export offline-disk-store (Available)
    Export region data from an offline disk store into Geode snapshot files.
export stack-traces (Not Available)
    Export the stack trace for a member or members.
gc (Not Available)
    Force GC (Garbage Collection) on a member or members. The default is for garbage collection to occur on all caching members.
get (Not Available)
    Display an entry in a region. If using a region whose key and value classes have been set, then specifying --key-class and --value-class
    is unnecessary.
help (Available)
    Display syntax and usage information for all commands or list all available commands if <command> isn't specified.
hint (Available)
    Provide hints for a topic or list all available topics if "topic" isn't specified.
history (Available)
    Display or export previously executed GFSH commands.
import cluster-configuration (Not Available)
    Imports configuration into cluster configuration hosted at the locators
import data (Not Available)
    Import user data from a file to a region.
list async-event-queues (Not Available)
    Display the Async Event Queues for all members.
list clients (Not Available)
    Display list of connected clients
list data-source (Not Available)
    (Experimental) List each existing data source.
list deployed (Not Available)
    Display a list of JARs that were deployed to members using the "deploy" command.
list disk-stores (Not Available)
    Display disk stores for all members.
list drivers (Available)
    (Experimental) Lists all drivers currently registered by the cluster's Driver Manager.
list durable-cqs (Not Available)
    List durable client cqs associated with the specified durable client id.
list functions (Not Available)
    Display a list of registered functions. The default is to display functions for all members.
list gateways (Not Available)
    Display the Gateway Senders and Receivers for a member or members.
list indexes (Not Available)
    Display the list of indexes created for all members.
list jdbc-mappings (Not Available)
    (Experimental) Display JDBC mappings for all members.
list jndi-binding (Not Available)
    List all jndi bindings, active and configured. An active binding is one that is bound to the server's jndi context (and also listed in
    the cluster config). A configured binding is one that is listed in the cluster config, but may not be active on the servers.
list lucene indexes (Not Available)
    Display the list of lucene indexes created for all members.
list members (Not Available)
    Display all or a subset of members.
list regions (Not Available)
    Display regions of a member or members.
load-balance gateway-sender (Not Available)
    Cause the Gateway Sender to close its current connections so that it reconnects to its remote receivers in a more balanced fashion.
locate entry (Not Available)
    Identifies the location, including host, member and region, of entries that have the specified key.
netstat (Not Available)
    Report network information and statistics via the "netstat" operating system command.
pause gateway-sender (Not Available)
    Pause the Gateway Sender on a member or members.
pdx rename (Available)
    Renames PDX types in an offline disk store. 
     Any pdx types that are renamed will be listed in the output. 
     If no renames are done or the disk-store is online then this command will fail.
put (Not Available)
    Add/Update an entry in a region. If using a region whose key and value classes have been set, then specifying --key-class and
    --value-class is unnecessary.
query (Not Available)
    Run the specified OQL query as a single quoted string and display the results in one or more pages. Limit will default to the value
    stored in the "APP_FETCH_SIZE" variable. Page size will default to the value stored in the "APP_COLLECTION_LIMIT" variable.
exit (Available)
    Exit GFSH and return control back to the calling process.
rebalance (Not Available)
    Rebalance partitioned regions. The default is for all partitioned regions to be rebalanced.
register driver (Available)
    (Experimental) Register a driver with the cluster's Driver Manager using the name of a driver class contained within a currenly deployed
    jar.
remove (Not Available)
    Remove an entry from a region. If using a region whose key class has been set, then specifying --key-class is unnecessary.
restore redundancy (Not Available)
    Restore redundancy and optionally reassign primary bucket hosting for partitioned regions in connected members. The default is for all
    regions to have redundancy restored and for primary buckets to be reassigned for better load balance.
resume async-event-queue-dispatcher (Not Available)
    Resume the processing of the events in the Async Event Queue on a member or members.
resume gateway-sender (Not Available)
    Resume the Gateway Sender on a member or members.
revoke missing-disk-store (Not Available)
    Instructs the member(s) of a distributed system to stop waiting for a disk store to be available. Only revoke a disk store if its files
    are lost as it will no longer be recoverable once revoking is initiated. Use the "show missing-disk-store" command to get descriptions
    of missing disk stores.
run (Available)
    Execute a set of GFSH commands. Commands that normally prompt for additional input will instead use default values.
search lucene (Not Available)
    Search lucene index
set variable (Available)
    Set GFSH variables that can be used by commands. For example: if variable "CACHE_SERVERS_GROUP" is set then to use it with "list
    members", use "list members --group=${CACHE_SERVERS_GROUP}". The "echo" command can be used to know the value of a variable.
sh (Available)
    Allows execution of operating system (OS) commands. Use '&' to return to gfsh prompt immediately. NOTE: Commands which pass output to
    another shell command are not currently supported.
show dead-locks (Not Available)
    Display any deadlocks in the Geode distributed system.
show log (Not Available)
    Display the log for a member.
show metrics (Not Available)
    Display or export metrics for the entire distributed system, a member or a region.
show missing-disk-stores (Not Available)
    Display a summary of the disk stores that are currently missing from a distributed system.
show subscription-queue-size (Not Available)
    Shows the number of events in the subscription queue.  If a cq name is provided, counts the number of events in the subscription queue
    for the specified cq.
shutdown (Not Available)
    Stop all members.
sleep (Available)
    Delay for a specified amount of time in seconds - floating point values are allowed.
start gateway-receiver (Not Available)
    Start the Gateway Receiver on a member or members.
start gateway-sender (Not Available)
    Start the Gateway Sender on a member or members.
start jconsole (Available)
    Start the JDK's JConsole tool in a separate process. JConsole will be launched, but connecting to Geode must be done manually.
start jvisualvm (Available)
    Start the JDK's Java VisualVM (jvisualvm) tool in a separate process. Java VisualVM will be launched, but connecting to Geode must be
    done manually.
start locator (Available)
    Start a Locator.
start pulse (Available)
    Open a new window in the default Web browser with the URL for the Pulse application.
start server (Available)
    Start a Geode Cache Server.
start vsd (Available)
    Start VSD in a separate process.
status cluster-config-service (Not Available)
    Displays the status of cluster configuration service on all the locators with enable-cluster-configuration set to true.
status gateway-receiver (Not Available)
    Display the status of a Gateway Receiver.
status gateway-sender (Not Available)
    Display the status of a Gateway Sender.
status locator (Available)
    Display the status of a Locator. Possible statuses are: started, online, offline or not responding.
status redundancy (Not Available)
    Report the redundancy status for partitioned regions in connected members. The default is to report status for all regions.
status server (Available)
    Display the status of a Geode Cache Server.
stop gateway-receiver (Not Available)
    Stop the Gateway Receiver on a member or members.
stop gateway-sender (Not Available)
    Stop the Gateway Sender on a member or members.
stop locator (Available)
    Stop a Locator.
stop server (Available)
    Stop a Geode Cache Server.
undeploy (Not Available)
    Undeploy JARs from a member or members.
upgrade offline-disk-store (Available)
    Upgrade an offline disk store. If the disk store is large, additional memory may need to be allocated to the process using the
    --J=-Xmx??? parameter.
validate offline-disk-store (Available)
    Scan the contents of a disk store to verify that it has no errors.
version (Available)
    Display product version information.
wan-copy region (Not Available)
    Copy a region with a senderId via WAN replication
```
