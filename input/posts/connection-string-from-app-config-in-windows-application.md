Title: Connection string from app.config in windows application
Published: 05/24/2017
Category:     Microsoft, MS .Net
Tags: C# MS.Net
---

In windows application configuration file, connection strings for your database can be stored as key/value pairs in the connectionStrings section of the configuration element.

```xml
<configuration>
  <connectionStrings>
    <add name="MyDBConnection" connectionString="Server=xxxx; UID=xxxx; PWD=xxxx; Database=xxxx;" />
  </connectionStrings>
</configuration>
```

To access your connection string from the configuration file you need to use the following code.

```cs
string connectionString = ConfigurationManager.ConnectionStrings["MyDBConnection"].ConnectionString;
```

The ConfigurationManager class in included with in the System.Configuration namespace.

```cs
using System.Configuration;
```

After the using statement included, compiler says that

>“The name ‘ConfigurationManager’ does not exist in the current context”.

To resolve this problem you need to add reference to “C:\Windows\Microsoft.NET\Framework\<Version Folder>\System.configuration.dll” using following steps. (Eg: C:\Windows\Microsoft.NET\Framework\v4.0.30319\System.Configuration.dll)
Goto Project -> Add References…

Switch to “Assemblies” tab in ‘Add Reference’ window, and select System.Configuration and click OK to add reference in your project.(you can search “System.Configuration” to locate the reference)

 Now the connection string from app.config file will be accessed using above code.

