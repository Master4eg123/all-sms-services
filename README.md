[![](https://img.shields.io/github/license/rattzv/all-sms-services)](https://license)
[![](https://img.shields.io/badge/service-sms--activate-red.svg)](https://sms-activate.ru/?ref=131777)
<p align="center">
  <img src="https://sun1-86.userapi.com/UR7honv-VPfHipG5NBALuYUNOFiA8dtaLXv3mA/ajGvDqa6SeY.jpg">
</p>

# Table of contents
* [Introduction](#Introduction)
* [Installation](#Installation)
* [Getting started](#Getting-started)
* [Documentation](#Documentation)
    * [SMS-ACTIVATE.RU](#sms-activateru)
    * [5SIM.NET](#5simnet)
* [Donate](#Donate)
* [Reporting Bugs](#Reporting-Bugs)
* [Contacts](#Contacts)
* [License](#The-MIT-License)

# Introduction
This library provides a pure C# interface for working with the [API](https://en.wikipedia.org/wiki/API) of popular virtual number services.  
In addition to the pure API implementation, this library features a number of high-level classes to make the development easy and straightforward.

# Installation
### Installing via NuGet
The easiest way to install **sms-services-lib** is via `NuGet`.
In Visual Studio's [Package Manager Console](http://docs.nuget.org/docs/start-here/using-the-package-manager-console), enter the following command:
```
Install-Package sms-services-lib
```

### Getting the Source Code
You'll need to clone MailKit from my GitHub repository. To do this using the command-line version of Git, you'll need to issue the following command in your terminal:
```
git clone --recursive https://github.com/jstedfast/MailKit.git
```

# Getting started
In the chapter [Documentation](#Documentation) you will find a description of all services and their methods. This example uses the `sms-activate.ru` service:
### Client initialization:

```csharp
SMSActivate client = SMSActivate.InitializeClient("api-key");
```
>`api-key` - required input parameter.  

Further work with the library takes place through the `client`.
### Balance check:
```csharp
string balance = client.GetBalance();
```
# Documentation

#### SMS-ACTIVATE.RU
Homepage service - [sms-activate.ru](https://sms-activate.ru/?ref=131777)
- **Methods**  
  - Available balance request - **GetBalance()**
    ```csharp
    SMSActivate client = SMSActivate.InitializeClient("api-key");
    string balance = client.GetBalance();
    ```
- **Available countries and services**

  All available countries and services/products are listed in enum. You just need to select the desired country and service from the list and pass it to the method, like this:
  ```csharp
  Countries countryName = Countries.Russia;
  Services serviceName = Services.Telegram
  vat t = client.GetNumberStatus(countryName, Services.Telegram)
  ```
  > `countryName` - required input parameter.
  > `serviceName` - required input parameter.
  However, this is not the only use case. You can also pass string parameters to the method, in accordance with the accepted on the site:
  ```csharp
  vat t = client.GetNumberStatus("0", "tg")
  ```
- **Exceptions**
  - NoBalanceErrorException

#### 5SIM.NET
# Donate
# Reporting Bugs
# Contacts
# The MIT License

Copyright © `2020` `Rattz Vadim`

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the “Software”), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.
