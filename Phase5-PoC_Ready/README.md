## Denodo Platform Installation
### On-Premise
1. Denodo Platform Servers (VDP, Denodo Scheduler, Data Catalog)
    - Hardware Requirements:
        - 4 Core CPU, 8 Core CPU for high load scenario
        - 16 GB RAM, 8 GB for the runtime heap space
        - 5 GB Disk, recommended 20 GB
    - Software Requirements:
        - OS (Windows/Linux) with Java support
        - Chrome 62.x, Edge 41.x, Firefox 57.x
    - Open default ports VDP:
        - 10091 (License Manager)
        - 9999 (Server)
        - 9996 (ODBC)
        - 9998 (Shutdown)
        - 9997 (JMX Monitoring)
        - 9995 (JMX Auxiliary Monitoring)
    - Open default ports Scheduler:
        - 8000 (Server)
        - 7999 (Shutdown)
        - 7998 (JMX Auxiliary Monitoring)
    - Open default ports Web Container:
        - 9090 (HTTP)
        - 9099 (Shutdown)
        - 9098 (JMX Monitoring)
        - 9097 (JMX Auxiliary Monitoring)
2. Denodo Solution Manager (Solution Manager, License Manager, and Solution Manager Administration Tool)
    - Hardware Requirements:
        - 4 Core CPU
        - 16 GB RAM
        - 5 GB Disk
    - Software Requirements:
        - OS (Windows/Linux) with Java support
        - Chrome 62.x, Edge 41.x, Firefox 57.x
    - Open default ports:
        - 19999 (Server)
        - 19998 (Shutdown)
        - 19996 (ODBC)
        - 19997 (JMX Monitoring)
        - 19995 (JMX Auxiliary Monitoring)
3. Denodo Express

## Folder Distribution
1. Configuration Files : conf
2. Binaries : bin
3. Logs : logs
4. Utilities : resources, samples, tools, webapps, work
5. Internal Folders : dll, jre, licenses, metadata, patches, setup, temp

## Denodo Control Center
Allows start and stop all denodo platform server and tools.
PS : Denodo Platform and Denodo Solution Manager have different Denodo Control Center.
### Denodo Platform Control Center
1. How to start in 3 methods:
    - From desktop shortcuts created during installation.
    - From application menus of the OS.
    - Executing : <DENODO_HOME>/bin/denodo_platform.{bat,sh}
2. What we need to configure :
    a. JVM
    b. License Manager
        - Connect to host, or
        - Use a license file
    c. Enable/Disable Security Token Authentication
        - Use SSL/TLS
        - Single Sign On (SSO) for Web Apps
    d. Web Container Config:
        - Include port-port number to configure
3. Update Platform
4. Uninstall Platform
5. VDP Control:
    - Start/stop VDP Server (9999)
    - Start/stop Data Catalog (http://127.0.0.1:9090/denodo-data-catalog)
    - Start/stop Web Design Studio (http://127.0.0.1:9090/denodo-design-studio)
    - Start/stop Diagnostic & Monitoring Tool (http://127.0.0.1:9090/diagnostic-monitoring-tool)
    - Launch VDP Administration Tools
6. Scheduler:
    - Scheduler Server (8000)
    - Scheduler Index Server (9000)
    - Scheduler Administration Tool (http://127.0.0.1:9090/web/admin/denodo-scheduler-administration-tool)

### Denodo Solution Manager Control Center
1. What to configure :
    a. JVM
    b. Choose license file
    c. Web Container Configuration Port
        - HTTP (19090)
        - Shutdown (19099)
        - JMX (19098)
        - Auxiliary (19097)
2. Solution Manager :
    a. Start/stop license manager server (10091)
    b. Start/stop solution manager server (10090)
    c. Start/stop solution manager administration tool (http://127.0.0.1:9090/solution-manager-web-tool)

### Control Center Quiz
1. How can you configure the JVM options of each Denodo server using the Denodo Control Center?
    - Click configure and then, JVM options.
2. Which of the following components can not be installed using the Denodo Control Center?
    - A custom component for the Virtual DataPort server.

## Starting Denodo Servers and Tools
### Quiz
1. What represents a server in the Solution Manager?
    - A server in the Solution Manager represents a specific service (included in an installation of the Denodo Platform).
2. What represents a cluster in the Solution Manager?
    - A cluster is a group of Denodo servers that belong to the same environment.
3. What represents an environment in the Solution Manager?
    - An environment is each one of the stages in a defined lifecycle that any change in the infrastructure has to surpass until it finally reaches production.

## Denodo Updates
Available in 3 different sections:
    - Updates : Add new enhancements and fix issues to a specific version of the Denodo Platform
    - Beta Updates : Early access versions of Denodo Platform updates only intended for testing purposes
    - Hotfixes : Temporary solutions to address specific customer requests
### Solution Manager

### Denodo Platform