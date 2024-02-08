## Personal repo on dotnet utils. This serves mostly as a personal reference. 

Check the dotnet versions installed on a system

```
dotnet --list-sdks
```

Create a new project
```
dotnet new console -n MFA_Testing
```

To check the generated files:
```
dotnet new <args> --dry-run
```

Add NuGet packages
```
dotnet add package Selenium.WebDriver --version 4.16.2
```

List NuGet packages of the solution
```
dotnet list package
```
# NuGet packages
|      Package         |  Version | 
|        ---           |    ---   |
| Selenium.WebDriver   |  4.16.2  |

# Gecko Driver Version
```
./geckodriver --version
```



```
https://learn.microsoft.com/en-us/aspnet/identity/overview/features-api/two-factor-authentication-using-sms-and-email-with-aspnet-identity
```
```
dotnet new web -o Microsoft_Identity
```
```
dotnet new gitignore
```
```
dotnet add package Microsoft.AspNet.Identity.Samples --prerelease
```
Errors: 
```
/Users/petrosportokalakis/ThesisApps/Microsoft_Identity/Microsoft_Identity.csproj : error NU1605: Warning As Error: Detected package downgrade: Microsoft.Owin.Security.Cookies from 3.0.1 to 2.1.0. Reference the package directly from the project to select a different version.
/Users/petrosportokalakis/ThesisApps/Microsoft_Identity/Microsoft_Identity.csproj : error NU1605:  Microsoft_Identity -> Microsoft.AspNet.Identity.Samples 2.2.0-alpha1 -> Microsoft.AspNet.Identity.Owin 2.2.2 -> Microsoft.Owin.Security.Cookies (>= 3.0.1)
/Users/petrosportokalakis/ThesisApps/Microsoft_Identity/Microsoft_Identity.csproj : error NU1605:  Microsoft_Identity -> Microsoft.AspNet.Identity.Samples 2.2.0-alpha1 -> Microsoft.Owin.Security.Cookies (>= 2.1.0)
/Users/petrosportokalakis/ThesisApps/Microsoft_Identity/Microsoft_Identity.csproj : error NU1605: Warning As Error: Detected package downgrade: Newtonsoft.Json from 6.0.4 to 5.0.6. Reference the package directly from the project to select a different version.
/Users/petrosportokalakis/ThesisApps/Microsoft_Identity/Microsoft_Identity.csproj : error NU1605:  Microsoft_Identity -> Microsoft.AspNet.Identity.Samples 2.2.0-alpha1 -> Microsoft.AspNet.Identity.Owin 2.2.2 -> Microsoft.Owin.Security.OAuth 3.0.1 -> Newtonsoft.Json (>= 6.0.4)
/Users/petrosportokalakis/ThesisApps/Microsoft_Identity/Microsoft_Identity.csproj : error NU1605:  Microsoft_Identity -> Microsoft.AspNet.Identity.Samples 2.2.0-alpha1 -> Newtonsoft.Json (>= 5.0.6)

The build failed. Fix the build errors and run again.
```
Solved with:
```
https://stackoverflow.com/questions/50286990/error-nu1605-detected-package-downgrade
```
By:
Adding `<NoWarn>NU1605</NoWarn>` in the `Microsoft_Identity/Microsoft_Identity.csproj` file.

That is, changes were:
```
    <!-- Microsoft.Owin.Security -->
    <PackageReference Include="Microsoft.Owin.Security" Version="3.0.1">
    <NoWarn>NU1605</NoWarn>
    </PackageReference>

    <!--Microsoft.Owin.Security.Cookies-->
    <PackageReference Include="Microsoft.Owin.Security.Cookies" Version="3.0.1">
    <NoWarn>NU1605</NoWarn>
    </PackageReference>

    <!--Newtonsoft.Json-->
    <PackageReference Include="Newtonsoft.Json" Version="6.0.4">
    <NoWarn>NU1605</NoWarn>
    </PackageReference>
```

Make project to use SSL:

```
dotnet run -lp https
```
Why?
```
HTTPS is HTTP with encryption and verification. The only difference between the two protocols is that HTTPS uses TLS (SSL) to encrypt normal HTTP requests and responses, and to digitally sign those requests and responses. As a result, HTTPS is far more secure than HTTP.
```


# Mozilla Version Used by Selenium

```
Console.WriteLine("Firefox browser version is: {0}", driver.Capabilities["browserVersion"]);
```

In general, the `driver.Capabilities` is a JSON object with the following information: 

```
{
  "acceptInsecureCerts": false,
  "browserName": "firefox",
  "browserVersion": "121.0.1",
  "moz:accessibilityChecks": false,
  "moz:buildID": "20240108143603",
  "moz:geckodriverVersion": "0.34.0",
  "moz:headless": true,
  "moz:platformVersion": "23.0.0",
  "moz:processID": 9151,
  "moz:profile": "/var/folders/c7/zmlbydts2h3_qq6_d8sbxgmc0000gn/T/rust_mozprofilefKwz08",
  "moz:shutdownTimeout": 60000,
  "moz:webdriverClick": true,
  "moz:windowless": false,
  "pageLoadStrategy": "normal",
  "platformName": "mac",
  "proxy": {},
  "setWindowRect": true,
  "strictFileInteractability": false,
  "timeouts": {
    "implicit": 0,
    "pageLoad": 300000,
    "script": 30000
  },
  "unhandledPromptBehavior": "dismiss and notify"
}
```
