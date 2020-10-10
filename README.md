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
The easiest way to install **sms-services-kit** is via `NuGet`.
In Visual Studio's [Package Manager Console](http://docs.nuget.org/docs/start-here/using-the-package-manager-console), enter the following command:
```
Install-Package sms-services-lib
```

### Getting the Source Code
You'll need to clone **sms-service-kit** from my GitHub repository. To do this using the command-line version of Git, you'll need to issue the following command in your terminal:
```
git clone --recursive https://github.com/rattzv/sms-service-kit.git
```

# Getting started
In the chapter [Documentation](#Documentation) you will find a description of all services and their methods. This example uses the `sms-activate.ru` service:
### Client initialization:

```csharp
SMSActivateCore client = SMSActivate.InitializeClient("api-key");
```
>`api-key` - required input parameter.  

Further work with the library takes place through the `client`.
### Balance check:
```csharp
string balance = client.GetBalance();
```
# Documentation

### SMS-ACTIVATE.RU
Homepage service - [sms-activate.ru](https://sms-activate.ru/?ref=131777)
- **Methods**  
  - Available balance request - **GetBalance()**
    ```csharp
    SMSActivateCore client = SMSActivate.InitializeClient("api-key");
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
    `serviceName` - required input parameter.
  <details>
  <summary>List of countries</summary>
        Russia = 0,
        Ukraine = 1,
        Kazakhstan = 2,
        China = 3,
        Philippines = 4,
        Myanmar = 5,
        Indonesia = 6,
        Malaysia = 7,
        Kenya = 8,
        Vietnam = 10,
        Kyrgyzstan = 11,
        US = 12,
        Israel = 13,
        HongKong = 14,
        Poland = 15,
        England = 16,
        Madagascar = 17,
        DemCongo = 18,
        Nigeria = 19,
        Macau = 20,
        Egypt = 21,
        India = 22,
        Ireland = 23,
        Cambodia = 24,
        Laos = 25,
        Haiti = 26,
        CotedIvoire = 27,
        Gambia = 28,
        Serbia = 29,
        Yemen = 30,
        SouthAfrica = 31,
        Romania = 32,
        Colombia = 33,
        Estonia = 34,
        Azerbaijan = 35,
        Canada = 36,
        Morocco = 37,
        Ghana = 38,
        Argentina = 39,
        Uzbekistan = 40,
        Cameroon = 41,
        Chad = 42,
        Germany = 43,
        Lithuania = 44,
        Croatia = 45,
        Sweden = 46,
        Iraq = 47,
        Netherlands = 48,
        Latvia = 49,
        Austria = 50,
        Belarus = 51,
        Thailand = 52,
        SaudArabia = 53,
        Mexico = 54,
        Taiwan = 55,
        Spain = 56,
        Iran = 57,
        Algeria = 58,
        Bangladesh = 60,
        Senegal = 61,
        Turkey = 62,
        CzechRepublic = 63,
        SriLanka = 64,
        Peru = 65,
        Pakistan = 66,
        NewZealand = 67,
        Guinea = 68,
        Mali = 69,
        Venezuela = 70,
        Ethiopia = 71,
        Brazil = 73,
        Afghanistan = 74,
        Uganda = 75,
        Angola = 76,
        Cyprus = 77,
        France = 78,
        PapuaNewGuinea = 79,
        Mozambique = 80,
        Nepal = 81,
        Belgium = 82,
        Bulgaria = 83,
        Hungary = 84,
        Moldova = 85,
        Italy = 86,
        Paraguay = 87,
        Honduras = 88,
        Tunisia = 89,
        Nicaragua = 90,
        TimorLeste = 91,
        Bolivia = 92,
        CostaRica = 93,
        Guatemala = 94,
        UAE = 95,
        Zimbabwe = 96,
        PuertoRico = 97,
        Sudan = 98,
        Togo = 99,
        Kuwait = 100,
        ElSalvador = 101,
        Libya = 102,
        Jamaica = 103,
        TrinidadAndTobago = 104,
        Ecuador = 105,
        Swaziland = 106,
        Oman = 107,
        BosniaAndHerzegovina = 108,
        DominicanRepublic = 109,
        Syria = 110,
        Qatar = 111,
        Panama = 112,
        Cuba = 113,
        Mauritania = 114,
        SierraLeone = 115,
        Jordan = 116,
        Portugal = 117,
        Burundi = 119,
        Benin = 120,
        Bahamas = 122,
        Botswana = 123,
        Grenada = 127,
        Georgia = 128,
        Greece = 129,
        GuineaBissau = 130,
        Guyana = 131,
        SaintKittsandNevis = 134,
        Lesotho = 136,
        Malawi = 137,
        Namibia = 138,
        Niger = 139,
        Rwanda = 140,
        Tajikistan = 143,
        Bahrain = 145,
        Reunion = 146,
        Zambia = 147,
        Somalia = 149,
        BurkinaFaso = 152,
        Gabon = 154,
        Norway = 174
  ```
  long console output here
  ```
</details>

  However, this is not the only use case. You can also pass string parameters to the method, in accordance with the accepted on the site:
  ```csharp
  int numbersCount = client.GetNumberStatus("0", "tg");
  ```
- **Exceptions**
  - **BadKeyErrorException**  
    The exception that is thrown when the `API-Key` is entered incorrectly.
    ```csharp
    try
    {
      SMSActivateCore client = SMSActivate.InitializeClient("invalidAPIKey");
    }
    catch(BadKeyErrorException)
    {
      Console.Writeline("Invalid API-Key");
    }
    ```

### 5SIM.NET
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
