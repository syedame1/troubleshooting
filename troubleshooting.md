```
SRE Runbook steps to resolve IT Incidents
```
**Issue:** Middleware service unreachable

**Description:** The issue \"Middleware CI Middleware-inform: IIS instance is unreachable\" typically
indicates that the system is unable to establish a connection with the IIS (Internet Information
Services) instance. This could be due to various reasons such as network connectivity issues, the IIS
service not running, firewall blocking the connection, incorrect IIS configuration, or issues with the
application pool.

**Resolution steps:**

- Check Network Connectivity: Ensure that the server hosting the IIS instance is reachable
    over the network. You can use tools like ping or traceroute to verify this.
- Verify IIS Service: Check if the IIS service is running on the server. If not, try to start
    the service.
- Check Firewall Settings: Ensure that the firewall settings are not blocking the connection
    to the IIS instance.
- Review IIS Configuration: Check the IIS configuration to ensure that it is set up correctly.
- Check Application Pool: Ensure that the application pool associated with the IIS instance
    is running.
- Review Event Logs: Check the event logs for any errors or warnings related to the
    IIS instance.

**Issue:** Webpage not found

**Description:** Error 404 is a standard HTTP status code that indicates the server could not find the
requested website or application. This error is often caused by the user attempting to access a
page or application that doesn't exist on the server. It's also known as 'Not Found' error and is one
of the most common errors encountered on the internet.
The error can occur for several reasons. It could be due to a typo in the URL, an outdated link, or the
page or application might have been moved or deleted from the server. In some cases, the server itself
might be down or experiencing issues, leading to a 404 error.

**Resolution Steps:**

- Check the URL: The first step is to ensure that the URL you are trying to access is correct.
    A simple typo or incorrect syntax can lead to a 404 error.
- Clear Browser Cache: Sometimes, your browser cache might be causing the issue. Clear
    your browser cache and cookies and then try accessing the application again.
- Check your Internet Connection: A poor or unstable internet connection can also cause a
    404 error. Ensure that you have a stable internet connection.
- Update your Browser: If your browser is outdated, it might not be able to access
    certain applications. Make sure your browser is up-to-date.


- Contact the Website: If none of the above steps work, the problem might be with
    the website itself. Contact the website's administrator or support team for
    assistance.

**Issue:** FileSystem Space Utilization in windows OS

**Description:** The FileSystem Space Utilization for E: on a Server has exceeded Threshold issue
refers to the situation where the E: drive on a server has used up its allocated storage space. This
can cause a variety of problems, including slow server performance, inability to save new data,
and potential data loss.

**Resolution steps:**

- Identify the Issue: Use a disk space analyzer tool to identify the files and folders that
    are consuming the most space on the E: drive.
- Clean Up Unnecessary Files: Delete or move unnecessary files and folders from the E:
    drive to free up space. This could include temporary files, duplicate files, or old backups.
- Archive Old Files: If there are old files that are not frequently accessed but still need to
    be kept, consider archiving them to a different storage medium.
- Increase Disk Space: If the E: drive is frequently running out of space, consider increasing
    its capacity. This could involve adding a new hard drive to the server or resizing the
    existing partitions.
- Set Up Alerts: To prevent the issue from recurring, set up alerts to notify you when the
    E: drive is nearing its capacity.

**Issue:** FileSystem Space Utilization in Linux

**Description:** The /tmp directory in a Linux server is a temporary storage area, which is used by
the system and applications for storing temporary files. When the FileSystem Space Utilization
for /tmp exceeds the threshold, it indicates that the /tmp directory is running out of space.
This can cause system instability and application failures, as the system and applications may
not be able to create new temporary files in the /tmp directory.

**Resolution steps:**

- Login to the Linux server.
- Use the 'df - h' command to check the disk space usage. This command will display
    the percentage of disk space used in each partition.
- If the /tmp directory is indeed full, use the 'du - sh /tmp/*' command to check the size
    of each file in the /tmp directory. This will help identify large files that may be
    consuming significant space.
- Once the large files are identified, verify if these files are required or can be deleted. If
    they are not needed, use the 'rm' command to delete them.


- After deleting the files, recheck the disk space usage using the 'df - h' command. If the
    /tmp directory is still using a high percentage of disk space, it may be necessary to
    increase the size of the /tmp partition.
- If increasing the size of the /tmp partition is not possible, consider moving some of the
    /tmp files to another partition with more available space.

**Description:** When the file system space utilization on a Linux server for / (root) has exceeded
the threshold, it means that the root directory is running out of space. This can cause significant
issues, including system instability, inability to save new data, and potential data loss.

**Resolution steps:**

- Check Disk Space: Use the 'df' command to check the disk space utilization. This
    command will provide a summary of the disk usage on your Linux server.
- Identify Large Files: Use the 'du' command to identify the directories consuming large
    amounts of space. You can also use the 'find' command to locate files above a certain
    size.
- Clean Up Unnecessary Files: Remove unnecessary files or move them to a different
    location. You can use the 'rm' command to delete files and the 'mv' command to move
    files.
- Clean Up Log Files: Log files often consume a lot of space. Use the 'logrotate' utility to
    manage these files. This utility allows automatic rotation, compression, removal, and mailing
    of log files.
- Increase Disk Space: If cleaning up files doesn't free up enough space, consider
    increasing the disk space. You can do this by adding a new disk or expanding the existing
    disk.

**Issue:** High CPU utilization in Linux OS

**Description:** High CPU utilization on a Linux server indicates that processes are consuming more
CPU cycles than expected. This can lead to performance degradation and can even cause the
server to become unresponsive.

**Resolution steps:**

- Identify the Process: Use the 'top' command to identify the process that is causing high
    CPU utilization. This command will display the list of processes and their respective CPU
    usage.
- Analyze the Process: Once you have identified the process, analyze why it is consuming
    high CPU. This could be due to a bug in the application, inefficient code, or a sudden surge
    in traffic.


- Optimize/Debug the Process: If the process is part of an application, you may need to
    optimize the code or debug it to reduce CPU usage. If it's a system process, you may need
    to adjust its priority or limit its CPU usage.
- Monitor the System: After making changes, monitor the system to ensure that CPU
    usage has decreased and is stable. Use tools like 'sar', 'vmstat', or 'iostat' for this.
- Upgrade the System: If the high CPU usage is due to increased workload, you may need
    to upgrade your system or add more resources.

**Issue:** High CPU utilization in Windows OS

**Description:** High CPU utilization on a Windows Server indicates that the server's processor is
working at or near its maximum capacity. This can lead to slower response times, system
instability, and in severe cases, server failure. The issue can be caused by a variety of factors,
including running too many applications simultaneously, a single application consuming
excessive resources, or hardware limitations.

**Resolution steps:**

- Identify the Process: Use the Task Manager to identify the process that is causing high CPU
    utilization. Press Ctrl+Shift+Esc to open Task Manager, click on the 'Processes' tab, and
    sort by CPU to see the most resource-intensive processes.
- Analyze Server Performance: Use Performance Monitor (perfmon.exe) to analyze the
    server's performance. This tool provides detailed information about how programs
    running on your server affect its performance.
- Update Software: If a specific software is causing high CPU utilization, check for updates
    or patches that might fix the issue.
- Optimize Server: Optimize your server by disabling unnecessary services, adjusting for
    best performance, and ensuring your server is not running out of resources.
- Hardware Upgrade: If the server is consistently reaching its CPU threshold, it might be time
    to consider a hardware upgrade. Adding more CPU cores or upgrading to a more powerful
    CPU can help.
- Consult with a Professional: If the issue persists, it may be best to consult with a
    professional or your server provider for further assistance.

**Issue:** Ping failure for Windows server

**Description:** The issue of ping failure for a Windows server in SiteScope could be due to several
reasons. The most common reason is that the server might not be responding to ICMP echo


```
requests, also known as 'pings'. This could be due to the server's firewall settings, which might be
configured to block such requests for security reasons.
```
```
Resolution steps:
```
- Check Network Connection: Ensure that the server is connected to the network and
    the network is functioning properly.
- Firewall Settings: Check the firewall settings on the Windows server. The firewall might
    be blocking ICMP echo requests.
- Enable ICMP Echo Requests: If the firewall is not the issue, ensure that the server
    is configured to respond to ICMP echo requests.
- Test Ping: After making the necessary changes, test the ping again to see if the issue
    is resolved.

```
Description: The vAgentManager service is a crucial component of the Windows operating
system. It is responsible for managing various tasks and processes, ensuring that your system
runs smoothly. However, if this service is stopped, it can lead to several issues, including system
instability and performance degradation.
The most common reason for the vAgentManager service to stop is due to incorrect system
settings or irregularities in the Windows registry. It can also occur due to malware or virus
attacks.
```
```
Resolution steps:
```
- Open the Services window: Press the Windows key + R, type \"services.msc\" in the Run
dialog box, and then press Enter.
- Locate the vAgentManager service: In the Services window, scroll down to find
the vAgentManager service.
- Check the service status: If the service status is Stopped, you need to start it.
- Start the service: Right-click on the vAgentManager service and select Start from the context
menu.
- Verify the startup type: Ensure that the Startup type of the vAgentManager service is set to
Automatic. If not, right-click on the service, select Properties, and then set the Startup type to
Automatic.
- Restart your computer: After making these changes, restart your computer to ensure that the
changes take effect.

```
Issue: Windows Cluster heartbeat missing.
```
```
Description: The Windows Cluster heartbeat missing issue is a common problem that can
occur due to various reasons such as network connectivity issues, incorrect cluster
configuration, firewall settings, outdated network card drivers, etc.
```

The heartbeat is a signal sent between the nodes in a cluster to check if each node is running and
connected. If a node doesn't receive a heartbeat from another node within a specified period, it
assumes that the other node is down and starts the failover process.

**Resolution steps:**

- Check Network Connectivity: Ensure that all the nodes in the cluster are connected to
    the network. Check the network cables, switches, and routers for any faults.
- Validate Cluster Configuration: Use the Validate a Configuration wizard in the
    Failover Cluster Management snap-in to check the cluster configuration.
- Check Firewall Settings: Ensure that the firewall settings on all nodes are not blocking
    the cluster communication.
- Update Network Card Drivers: Update the network card drivers on all nodes to the
    latest version.
- Reconfigure Cluster: If all else fails, consider reconfiguring the cluster.

**Issue:** MSSQL Login issue using jdbc

**Description:** The issue \"Cannot login via JDBC to MSSQL DB Instance\" in SiteScope can occur
due to various reasons. The most common reason is incorrect JDBC connection string. The
connection string should include the correct database name, server name, port, and credentials.
If any of these details are incorrect, SiteScope will not be able to connect to the MSSQL server.
Another possible reason could be that the MSSQL server is not running or the machine where
SiteScope is installed cannot reach the MSSQL server over the network.The issue can also occur
if the login credentials provided in the JDBC connection string are incorrect.

**Tower:** MSSQL

**Resolution steps:**

- Check JDBC Connection String: Ensure that the JDBC connection string is correct. It
should include the correct database name, server name, port, and credentials.
- Verify MSSQL Server Status: Make sure that the MSSQL server is up and running. You can
do this by trying to connect to the server using a tool like SQL Server Management Studio.
- Check Network Connectivity: Verify that the machine where SiteScope is installed can
reach the MSSQL server over the network. You can do this by pinging the server or using a
tool like telnet to check the connectivity on the specific port.
- Validate Login Credentials: Ensure that the username and password provided in the
JDBC connection string are correct. Try to login to the MSSQL server using these
credentials.
- Update JDBC Driver: If all the above steps are correct, then the issue might be with the JDBC
driver. Make sure that you are using the latest JDBC driver compatible with your MSSQL server
version.


```
Issue: DBFile Space Utlization
```
```
Description: The issue of MSSQL DBFile Space Utilization Exceeding Threshold (90%) for
Database tempdb in SQL Instance is a common one faced by database administrators. This
happens when the tempdb database, which is a system database in SQL Server, grows in size and
exceeds the set threshold, usually set at 90%. This can cause performance issues and can even
lead to the SQL Server instance running out of space.
The tempdb database is used by SQL Server for various tasks such as storing temporary tables
and stored procedures, and for sorting data. Therefore, it is normal for the size of the tempdb
database to fluctuate. However, if it consistently exceeds the threshold, it indicates a problem
that needs to be addressed.
```
```
Resolution Steps:
```
- Identify the Size of the Database: Use the SQL Server Management Studio to check the size of the
tempdb database. This can be done by right-clicking on the database, selecting Properties, and then
clicking on the General page.
- Check for Long Running Transactions: Long running transactions can cause the tempdb database
to grow. Use the DBCC OPENTRAN command to check for any long running transactions.
- Shrink the Database: If the tempdb database is too large, you can use the DBCC SHRINKDATABASE
command to reduce its size. However, this should be done with caution as it can cause performance
issues.
- Monitor the Database: Regularly monitor the size of the tempdb database to ensure it does
not exceed the threshold again. This can be done using SQL Server Management Studio or a third-
party monitoring tool.
- Increase the Size of the Database: If the tempdb database is regularly exceeding the threshold,
consider increasing its size. This can be done by right-clicking on the database, selecting
Properties, and then clicking on the Files page.

```
Issue: Backup failure
```
```
Description: The failure of MSSQL Backup for SQL Instance can occur due to various reasons such
as insufficient disk space, network issues, or SQL Server Agent service not running.
```
```
Resolution steps:
```
- Check SQL Server Error Logs: The first step is to check the SQL Server error logs. This
will provide detailed information about why the backup failed.
- Verify Backup Location: Ensure that the backup location is accessible and has enough space
to store the backup.
- Check SQL Server Agent: Verify if the SQL Server Agent service is running. If it's not, start
the service.


- Check Backup Job: If the backup is scheduled through a job, check the job history for
any errors.
- Update SQL Server: Ensure that the SQL Server is updated with the latest service packs
and patches.
- Consult with a DBA: If the issue persists, consult with a Database Administrator (DBA) or a
SQL Server expert.

**Issue:** Oracle error ORA- 00060

**Description:** The Oracle error ORA-00060 is a deadlock error that occurs when two or more
sessions are waiting for resources locked by each other, resulting in a circular wait condition. This

typically happens when concurrent sessions are trying to modify the same data in a
different order, causing each session to wait for the other to release the resource.

**Resolution steps:**

- Identify the Session: Use the following query to identify the session that is causing the
deadlock: SELECT p.spid, s.sid, s.serial#, s.username, s.program FROM v$session s JOIN
v$process p ON p.addr = s.paddr WHERE s.sid IN (SELECT session_id1 FROM
dba_blockers UNION ALL SELECT session_id2 FROM dba_waiters);
- Kill the Session: Once you have identified the session, you can kill it using the
following command: ALTER SYSTEM KILL SESSION 'sid,serial#';
- Check for Uncommitted Transactions: Uncommitted transactions can cause deadlocks. Use
the following query to check for uncommitted transactions: SELECT s.sid, s.serial#, s.username,
s.status, t.start_time FROM v$transaction t JOIN v$session s ON t.ses_addr = s.saddr;
- Resolve Row-Level Locking: If row-level locking is causing the deadlock, consider
using different sequences or modifying your application to avoid simultaneous updates.
- Use Automatic Deadlock Detection: Oracle Database automatically detects and resolves
deadlocks by rolling back one of the statements involved in the deadlock. This feature can
be enabled using the parameter \"DEADLOCK_TIMEOUT\".

**Issue:** SAP SID DEO: Internal Solution Manager Metric Collection Problem

**Description:** The SAP Solution Manager (SolMan) is a central support and system
management suite provided by SAP. It is used for implementing and operating complex
system landscapes, including SAP and non-SAP products. One of its key features is the
proactive alert system for Service Level Agreement (SLA) norms.


```
In this case, the SAP SolMan has triggered a proactive alert for the SAP System ID (SID) DEO,
indicating an internal Solution Manager Metric Collection problem. This means that the SolMan
is unable to collect the necessary metrics from the SAP SID DEO. These metrics are crucial for
monitoring the performance and health of the system, and any issues with their collection can
lead to serious problems.
The issue could be due to various reasons, such as problems with the SAP Solution Manager
itself, issues with the metric collection, incorrect SLA settings, or an outdated or incorrect SAP
SID.
```
```
Resolution steps:
```
- Check the SAP Solution Manager: Ensure that the SAP Solution Manager is running correctly.
Check the system logs for any errors or warnings that might indicate a problem.
- Verify the Metric Collection: Check if the metric collection is functioning properly. This can be
done by navigating to the monitoring and alerting infrastructure (MAI) and checking the status
of the metric collection.
- Check the SLA: Verify if the SLA is set correctly. If the SLA is not set or is set incorrectly, it
can cause the alert.
- Update the SAP SID: If the SAP SID is outdated or incorrect, it can cause the alert. Update
the SAP SID to the correct one.
- Restart the SAP Solution Manager: If all the above steps do not resolve the issue, restart
the SAP Solution Manager. This can resolve any temporary issues that might be causing the alert.

```
Issue: SAP SID DSO: Oracle Tablespace Full
```
```
Description: The issue at hand is a proactive alert from SAP Solution Manager (SolMan)
indicating that the Oracle Tablespace for the SAP SID DSO is full. This is a critical issue as it can
affect the performance and functionality of the SAP system. The Oracle Tablespace is a database
storage unit that groups related logical structures together. When it becomes full, it means that
there is no more space for the database to store data, which can lead to system errors and
performance issues.
```
```
Resolution steps:
```
- Identify the Issue: The first step is to identify the issue. In this case, the Oracle Tablespace
for the SAP SID DSO is full. This can be identified through the proactive alert from SAP Solution
Manager (SolMan).
- Analyze the Issue: The next step is to analyze the issue. This involves checking the Oracle
Tablespace to see what is causing it to be full. This could be due to a large amount of data, a
lack of space, or a problem with the database.
- Resolve the Issue: The third step is to resolve the issue. This could involve
deleting unnecessary data, increasing the size of the tablespace, or fixing the
database issue.


- Test the Solution: The fourth step is to test the solution to ensure that it has resolved
the issue. This could involve checking the Oracle Tablespace to see if it is no longer full.
- Monitor the Situation: The final step is to monitor the situation to ensure that the issue
does not reoccur. This could involve setting up alerts in SAP SolMan to notify you if the Oracle
Tablespace becomes full again.

**Issue:** SAP SID DEC: ABAP Instance not available

**Description:** The issue at hand pertains to the unavailability of the ABAP instance for the SAP
SID DEC. This is a critical issue as it hampers the normal functioning of the SAP Solution
Manager (SolMan) and can lead to a breach of the Service Level Agreement (SLA). The ABAP
instance is a crucial component of the SAP system, and its unavailability can disrupt the entire
system. The root cause of this issue could be a system crash, network issues, or a problem with
the database.

**Resolution steps:**

- Check the SAP system: The first step is to check the SAP system to identify the cause of
the issue. This could be due to a system crash, network issues, or a problem with the
database.
- Analyze the logs: The next step is to analyze the system logs to identify any errors or
warnings that could have led to the issue. This will help in pinpointing the exact cause of the
problem.
- Restart the SAP instance: If the issue is due to a system crash, the SAP instance may need
to be restarted. This should be done carefully to avoid any data loss.
- Check the network: If the issue is due to network problems, the network should be
checked and any issues should be resolved.
- Check the database: If the issue is due to a problem with the database, the database
should be checked and any issues should be resolved.
- Monitor the system: After the issue has been resolved, the system should be monitored
to ensure that the problem does not recur.

**Issue:** Oracle error ORA- 60

**Description:** The Oracle error ORA-60, also known as the deadlock detected error, occurs when
two or more sessions are waiting for resources locked by each other, resulting in a circular wait
condition. This is a serious issue as it can lead to performance degradation and can even halt the
system.

**Resolution steps:**


- Identify the Session: The first step is to identify the session that is causing the deadlock.
This can be done by querying the V$SESSION view in Oracle.
- Analyze the Trace File: Once the session is identified, the next step is to analyze the trace
file generated by Oracle. This file contains detailed information about the deadlock and can
help in identifying the root cause.
- Identify the Objects: The trace file will also contain information about the objects involved
in the deadlock. Identifying these objects can help in understanding the nature of the
deadlock.
- Resolve the Deadlock: Once the root cause is identified, the next step is to resolve the
deadlock. This can be done by either killing one of the sessions involved in the deadlock or
by modifying the application code to avoid such deadlocks in the future.
- Monitor the System: After resolving the deadlock, it is important to monitor the system
to ensure that the issue does not recur.

**Issue:** Oracle error ORA- 27037

**Description:** The Oracle error ORA- 27037 is a common error that occurs when Oracle is unable to
open a file. This error is often caused by issues with file permissions, file location, or disk space.
When Oracle tries to open a file and fails, it generates the ORA-27037 error. The error message
usually includes the name of the file that Oracle is trying to open. This information can be used
to identify the file and investigate the cause of the error. One common cause of the ORA- 27037

error is incorrect file permissions. The Oracle process needs to have read and write permissions
to the file. If the permissions are incorrect, Oracle will not be able to open the file, resulting in
the ORA-27037 error. Another common cause of the ORA-27037 error is an incorrect file
location. The file needs to be in the location specified in the error message. If the file is not in the
correct location, Oracle will not be able to find the file, resulting in the ORA- 27037 error. A full
disk can also cause the ORA-27037 error. If there is not enough disk space available, Oracle may
not be able to open the file.

**Resolution steps:**

- Identify the File: The first step is to identify the file that is causing the error. This can be
done by checking the error message, which usually includes the name of the file.
- Check File Permissions: Once the file is identified, check the permissions of the file. The
Oracle process should have read and write permissions to the file.
- Verify File Location: Verify the location of the file. The file should be in the location
specified in the error message.
- Check Disk Space: Check if there is enough disk space available. If the disk is full, it may
cause the ORA- 27037 error.
- Consult Oracle Documentation: If the error persists, consult Oracle documentation or
contact Oracle support for further assistance.


**Issue:** High Memory utilization in Windows OS

**Description:** Memory utilization crossing the threshold on a Windows server is a common issue
that can significantly slow down the system, causing applications to run inefficiently or even
crash. This issue arises when the memory usage exceeds the set limit, in this case, 95%.

**Resolution steps:**

- Identify the Processes Consuming High Memory: Open the Task Manager by pressing
Ctrl+Shift+Esc and go to the 'Processes' tab. Here, you can see which processes are
consuming the most memory.
- Close Unnecessary Applications: If there are any unnecessary applications running that
are consuming high memory, close them to free up some memory.
- Increase Virtual Memory: If the physical memory is not sufficient, you can increase the virtual
memory. Go to 'System Properties' > 'Advanced' > 'Performance Settings' > 'Advanced' >
'Change'. Uncheck 'Automatically manage paging file size for all drives', select 'Custom size' and
set the initial and maximum size for the paging file.
- Clean Up Disk: Use the built-in Disk Cleanup tool to remove unnecessary files from the
disk which can also help to free up some memory.
- Disable Startup Programs: Some programs start automatically when the system boots up
and consume memory. You can disable these startup programs from the Task Manager.
- Scan for Malware: Sometimes, malware can consume high memory. Use a reliable
antivirus program to scan and remove any potential malware.
- Update System and Drivers: Make sure your system and all drivers are up-to-date.
Sometimes, outdated drivers can cause high memory usage.

**Issue:** High Memory utilization in Linux OS

**Description:** Memory utilization crossing the threshold on a Linux server is a common issue that
can significantly impact the performance and stability of the server. This typically occurs when
one or more processes consume excessive memory, leaving little to no memory available for
other processes.

**Resolution steps:**

- Identify the Processes Using Memory: Use the 'top' command to identify the processes that
are consuming the most memory. This will help you understand which applications or services
are causing the high memory utilization.


- Analyze the Memory Usage: Use the 'free -m' command to analyze the memory usage.
This command will show you the total amount of free and used physical and swap memory
in the system.
- Optimize or Kill the Process: If a specific process is consuming too much memory, consider
optimizing the application or service. If it's not necessary, you can also kill the process using
the 'kill' command.
- Add More Memory: If the server is consistently reaching its memory capacity, it might be
time to add more memory to the server.
- Configure Swap Space: If your server is running out of physical memory, you can
configure swap space to provide a temporary relief.

**Issue:** App review pod failure

**Description:** The "BackOff" error signifies that the container named "review" within the pod "app-
review" has failed to start multiple times consecutively. Kubernetes employs exponential back-off
retry logic when a container repeatedly fails to start. In this scenario, the container is being
restarted, but it continues to fail, triggering the back-off mechanism.

**Resolution steps:**

- Identify the Processes Using Memory: Use the 'kubectl top pods' command to identify the
pods that are consuming the most memory. This will help you understand which pods are
causing the high memory utilization.
- Analyze the Memory Usage: Use the 'kubectl describe pod app-review' command to analyze
the memory usage of the failing pod. Look for the "Limits" and "Requests" sections to see the
current memory configuration.
- Optimize or Kill the Process: If the failing pod app-review is consuming too much memory,
consider optimizing the application or service running inside the pod. If optimization is not
feasible or immediate relief is needed, increase the memory allocation for the pod by
modifying the pod's YAML configuration file.
- Update Pod Configuration YAML: Modify the pod's YAML configuration file by increasing the
memory limit or request values under the resources section. The Playbook for this can be
found here:https://github.com/manikrishna01/DigiExpertRepo
- Apply Changes: Apply the modified configuration to the Kubernetes cluster using the
'kubectl apply - f <yaml_file>' command.
- Verify Changes: Verify that the changes have been applied successfully by checking the pod's
description again using 'kubectl describe pod app-review' and ensuring that the memory limits
and requests have been updated accordingly.

**Issue:** App review pod failure in k8 cluster


**Description:** The error indicates that the "app-review" pod within the "robot-shop" namespace
of the Kubernetes cluster is experiencing a recurring failure known as "crash loop backoff." This
occurs when the pod repeatedly fails to start and is automatically restarted by Kubernetes, only
to fail again, leading to a looped cycle of failures and restarts. The logs suggest that the failure is
related to memory constraints, as the pod is unable to run due to insufficient memory
allocation. This issue can lead to application downtime and service disruptions. To resolve it, the
memory allocation for the "app-review" pod needs to be increased to meet the application's
resource requirements, ensuring stable and uninterrupted operation.

**Resolution steps:**

- Identify the Pod: Based on the logs, the pod named "app-review" in the "robot-shop"
namespace is experiencing a crash loop backoff.
- Check Pod Resource Requests and Limits: Review the Ansible playbook "fix.yaml" to
understand the resource requirements specified for the "app-review" pod. The playbook
indicates a memory resource request of 150Mi and a limit of 200Mi.
- Inspect Cluster Resources: Before modifying the pod's resource allocation, assess the
current resource utilization of the cluster. Use tools like kubectl top nodes to check the overall
resource usage across the cluster nodes.
- Increase Memory Allocation: Given that the pod is failing due to insufficient memory
allocation, update the playbook to allocate more memory to the "app-review" pod.
- Modify the Playbook: Update the playbook to increase the memory resource request and
limit for the "app-review" pod. The Playbook can be found
here:https://github.com/manikrishna01/DigiExpertRepo
- Apply Changes: Apply the modified playbook to the Kubernetes cluster. Ensure to target the
correct cluster specified in the kubeconfig file and verify that the kubeconfig contains the
necessary permissions to make changes.
- Verify Pod Status: After applying the changes, verify the status of the "app-review" pod in
the "robot-shop" namespace using the 'kubectl get pods -n robot-shop' command. Ensure that
the pod is running without errors and is not experiencing a crash loop backoff.
- Monitor Pod Performance: Monitor the performance of the "app-review" pod to ensure
that it no longer experiences memory-related failures. Use tools like 'kubectl describe pod
<pod_name>' and 'kubectl logs <pod_name>' to inspect the pod's status and logs for any issues.
- Review Cluster Health: Periodically review the health and performance of the cluster to
ensure that the resource allocations are appropriate and meet the demands of the deployed
applications.


