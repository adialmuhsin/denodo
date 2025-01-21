# Denodo

### Who is Denodo?
Mission : make data universally accessible from diverse data sources.
Vision : provide companies with agile, efficient, and scalable data solutions.
Denodo is recognized as a leader in data virtualization and integration by Gartner and Forrester.
### Market Position
- Strong in Data Integration Vendor
- Specializing data virtualization
- Create logical data management architectures
- Data Security
- Data Governance
- AI Capabilities
### Core Use Cases
1. Data Self-Service for Data Democratization
2. IT Infrastructure Modernization
3. Data Foundation for Customer Experience
4. Improve Operational Efficiency, Agility, and Resilience
5. Centralize Governance, Risk, and Compliance
### Product and Services
Product:
1. Denodo Professional
2. Denodo Standard
3. Denodo Enterprise
4. Denodo Enterprise Plus
Services:
1. Professional Services
2. Support Services
    - Standard
    - Premium (Plus 24x7 global coverage, faster response, and extended version support)
3. Education Services
    - Denodo Community
    - Denodo Training
    - Denodo Certification
### Competitors
1. Tibco by Citrix (Main Competitors)
2. Starburst
3. Dremio
4. Snowflake
5. Databricks
### Platform Demonstration
Organization can:
1. Quickly find data using a Data Catalog, integrate it into a dataset
2. Ensure the right people have permission to use data
3. Share data through APIs or Bussiness Intelligence tools as per the user needs
4. Easily adapt to what a business needs
### Customer Stories
1. BHP (Mining Company) - Use Logical data Fabric to improve worker safety.
2. City Furniture
3. ESTES Express
### How to Present Denodo
1. Hybrid/Multi-Cloud Data Integration : Achieving a more flexible and scalable data infrastructure requires a modern data architecture.
2. Data Democratization/Self-Service Analytics : Making data more accessible and easier to analyze for a wider range of users.
3. Data Marketplace/Enterprise Data Services : Share data assets with internal and/or external users, facilitating data-driven collaboration and innovation.
4. 360 View of Entities : Gaining a comprehensive view of data for specific subject (e.g. customer, product, etc.)
5. Data Fabric : Provide a unified and integrated view of data across multiple distributed data sources and systems.
6. Data Mesh : Decentralization of data ownership, enabling organizations to scale data usage and analytics with a higher degree of agility and autonomy.
7. Governance and Compliance : Centrally manage, protect, and ensure the privacy, and security of your organization's data in accordance with regulatory requirements.
8. Data Science / AI / ML : Make it easy for your data scientist have real-time access to curated, high-quality data.
### Assesment
1. You are meeting with a friend working in a law firm, who asks you, "what does Denodo do?" What might be your best response?
    - We have 1000+ customers across a variety of industries (Wrong)
    - We provide companies with agile, efficient and scalable data management solutions to help them make more informed decisions (Correct)
2. You are chatting to someone who works in IT. They ask, "What is the technology that Denodo is based on and who are your competitors?" What might be an answer?
3. You find the CEO of a large bank standing next to you at a marketing event. When the CEO asks you "what Denodo does?", what might be your best answer?
    - Denodo is a leading vendor in data management and integration (Wrong)
    - Denodo helps business users to immediately and easily access the data they need without worrying about where it is housed, how it is formatted, or how quickly it changes. (Correct)
4. You are speaking with Sales Manager, who uses reports to make decisions about the sales regions needing more help to reach their goals. How might you best describe to this business user, what Denodo does?
5. Denodo advocates a logical approach to data integration. What is meant by a "logical approach"?
    - Integrating data by connecting directly to each source (Wrong)
    - Logically connecting to the data source and not moving the data physically (Correct)

## Installation
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
