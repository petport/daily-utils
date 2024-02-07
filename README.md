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


```
https://learn.microsoft.com/en-us/aspnet/identity/overview/features-api/two-factor-authentication-using-sms-and-email-with-aspnet-identity
```
dotnet new web -o Microsoft_Identity
```
```
dotnet new gitignore
```
```
dotnet add package Microsoft.AspNet.Identity.Samples --prerelease
```
```
./geckodriver --version
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
