# Configuring Connector Server

Connectors can be deployed in two ways:

* **Local connectors** are deployed to a Cymmetri instance. This is the usual way how connectors are used. The connector is executed inside a Cymmetri instance, has the same lifecycle (start/stop), etc. Cymmetri can detect local connectors automatically and overall the connector management is easier.
* **Remote connectors** are executed in a different process or on a different node than Cymmetri instance. Remote connectors are deployed to a connector server. There may be need to use a remote connector e.g. to access a file on a remote system (e.g. in case of CSV connector) or because of platform incompatibilities (e.g. .NET connectors)

Connector is **not** developed as local or remote. The placement of the connector is a deployment-time decision. There is just one connector package that can be deployed locally or remotely.

A connector server is required when a connector bundle is not directly executed within your application. By using one or more connector servers, the connector architecture thus permits your application to communicate with externally deployed bundles.

Connector servers are available for both Java and .NET.

A **Java connector server** is useful when you do not wish to execute a Java connector bundle in the same VM as your application. It may be beneficial to run a Java connector on a different host for performance improvements if the bundle works faster when deployed on the same host as the native managed resource. Additionally, one may wish to use a Java connector server under a Java remote connector server in order to eliminate the possibility of an application VM crash due to a fault in a JNI-based connector.

The use of **.NET connector server** is especially useful when an application is written in Java, but a connector bundle is written using C#. Since a Java application (e.g. J2EE application) cannot load C# classes, it is necessary to instead deploy the C# bundles under a .NET connector server. The Java application can communicate with the C# connector server over the network, and the C# connector server serves as a proxy to provide to any authenticated application access to the C# bundles deployed within the C# connector server.

## Java Connector Server

### Installing a Java Connector Server

Minimum Requirements:

* Java 1.6 or later for 1.4.X.Y / Java 1.8 for 1.5.X.Y
* Refer to your Java connectors to determine if there are any additional requirements&#x20;

#### Create your execution environment

* Download the Connector Server package
  * [1.3.3.1](https://repo1.maven.org/maven2/org/connid/connector-server-zip/1.3.3.1/connector-server-zip-1.3.3.1.zip)
  * [1.4.5.1](https://repo1.maven.org/maven2/net/tirasa/connid/connector-server-zip/1.4.5.1/connector-server-zip-1.4.5.1.zip)
  * [1.5.0.1](https://repo1.maven.org/maven2/net/tirasa/connid/connector-server-zip/1.5.0.1/connector-server-zip-1.5.0.1.zip)
  * [1.5.1.0](https://repo1.maven.org/maven2/net/tirasa/connid/connector-server-zip/1.5.1.0/connector-server-zip-1.5.1.0.zip)
* Unzip it in a directory of your choice (e.g. `/usr/jconnserv`) on the host where you wish to run the Java connector server

#### Test your execution environment

From the directory created above, run the Java connector server with no arguments to see the list of command-line options:

* Linux / MacOS: `./bin/ConnectorServer.sh`
* Windows: `\bin\ConnectorServer.bat`

You should see the following output:

```
Usage: 
  Main -run -properties 
  Main -setkey -key  -properties 
  Main -setDefaults -properties 
```

#### Configure your Java connector server

* Run the connector server with the `setkey` option as described below to set your desired key into your properties file
  * Linux/ MacOS: `./bin/ConnectorServer.sh -setkey <key> -properties conf/ConnectorServer.properties`
  * Windows:  `bin\ConnectorServer.bat /setkey <key> /properties conf\ConnectorServer.properties`
* For all other properties (e.g. port), edit the `conf/connectorserver.properties` manually. The available properties are described in the `connectorserver.properties` file.

### Running your Java connector server

Run the server by launching with the -run option:

* Linux / MacOS: `./bin/ConnectorServer.sh -run -properties conf/ConnectorServer.properties`
* Windows:  `bin\ConnectorServer.bat /run -properties conf\ConnectorServer.properties`

### Installing Connectors on a Java Connector Server

To deploy a Java connector:

* Copy the Java connector bundle jar file into the `bundles` directory in your Java connector server directory
* If necessary, add to the classpath any 3rd party jars required by any Java connector
* Restart the Java connector server

### Using SSL to communicate with connector servers

The following steps are necessary to successfully communicate with a connector server using SSL:

* Deploy an SSL certificate to the connector server's system.
* Configure your connector server to provide SSL sockets.
* Configure your application to communicate with the communicate with the connector server via SSL.

#### Configure your application to use SSL

Refer to your application manual for specific notes on how to configure connections to connector servers. You will need to indicate to your application that an SSL connection is required when establishing a connection for each SSL-enabled connector server.

Additionally, if any of the SSL certificates used by your connector servers is issued by a non-standard certificate authority, your application must be configured to respect the additional authorities. Refer to your application manual for notes regarding certificate authorities.

Java applications may solve the non-standard certificate authority issue by expecting that the following Java system properties are passed when launching the application:

* javax.net.ssl.trustStorePassword\
  For example, `-Djavax.net.ssl.trustStorePassword=changeit`
* javax.net.ssl.trustStore\
  For example, `-Djavax.net.ssl.trustStore=/usr/myApp_cacerts`

Or, instead, the non-standard certificate authorities may be imported to the standard ${JAVA\_HOME}/lib/security/cacerts.

## .NET Connector Server

### Installing a .NET Connector Server

Minimum Requirements:

* Windows Server 2003 or 2008
* .NET Framework 3.5 or higher
* Refer to your .NET connector to determine if there are any additional requirements

Execute **ServiceInstall.msi**. Just follow the wizard. It will walk you through the whole process step by step. Upon completion, the Connector Server will be installed as a windows service.

### Configuring the .NET Connector Server

Start the Microsoft Services Console. Check to see if the Connector Server is currently running. If so, stop it. From a command prompt, set the key for the connector Server. This is done by changing to the directory where the connector server was installed (by default: \Program Files\Identity Connectors\Connector Server) and executing the following command:

```
ConnectorServer /setkey <newkey>
```

where \<newkey> is the value for the new key. This key is required by any client that connects to this Connector Server.

Look through the configuration file and inspect all settings. The most common things to change would be the port, trace, and ssl settings.

#### Additional Notes about configuration

The port, address, and SSL settings are in the tag called `AppSettings`, and look like this:

```
<add key="connectorserver.port" value="8759" />
<add key="connectorserver.usessl" value="false" />

<add key="connectorserver.certificatestorename" value="ConnectorServerSSLCertificate" />
<add key="connectorserver.ifaddress" value="0.0.0.0" />
```

The port can be set by changing the value of connectorserver.port. The listening socket can be bound to a particular address, or can be left as 0.0.0.0. To setup to use SSL, you must set the value of connectorserver.usessl to true, and then set the value ofconnectorserver.certifacatestorename to your the certificate store name.

You will need to record for use later the following information regarding your connector server installation:

* Host name or IP address
* Connector server port
* Connector server key
* Whether SSL is enabled

#### Changing Trace Settings

Trace settings are in the configuration file. The settings look like this:

```
<system.diagnostics>
  <trace autoflush="true" indentsize="4">
     <listeners>
       <remove name="Default" />
       <add name="myListener" type="System.Diagnostics.TextWriterTraceListener"
  initializeData="c:\connectorserver2.log" traceOutputOptions="DateTime">        
         <filter type="System.Diagnostics.EventTypeFilter" initializeData="Information" />
       </add>
    </listeners>
  </trace>
</system.diagnostics>
```

The Connector Server uses the the standard .NET trace mechanism. For more information about the tracing options, see Microsoft's .NET documentation for System.Diagnostics.

The default settings are a good starting point, but for less tracing, you can change the EventTypeFilter's initializeData to "Warning" or "Error". For very verbose logging you can set the value to "Verbose" or "All". The amount of logging performed has a direct effect on the performance of the Connector Servers, so be careful of the setting.

Any configuration changes will require the connector server to be stopped and restarted.

### Running the .NET Connector Server

The best way to run the Connector Server is as a Windows service. When installing, the Connector Server is installed as a Windows service. This should be fine for most installations.

If for some reason, this is not adequate, the connector server may be installed or uninstalled as a Windows service by using the /install or /uninstall arguments on the command line. To run the Connector Server interactively, issue the command:

```
ConnectorServer /run
```

#### Installing Connectors on a .NET Connector Server

To install new connectors, change to the directory where the Connector Server was installed, and unzip the zip file containing the connector there. Restart the Connector Server.

#### Running Multiple Connector Servers on the Same Machine

To install additional Connector Servers on the same machine, download the Connector Server zip file from the downloads section. Create a directory to install to, and unzip the file there. Edit the configuration file as described above ensuring that you have a unique port. You may also want to make sure that the trace file is different as well. You can then run the additional Connector Server interactively or as a service.
