---
title: Azure Billing SDK for .NET
description: Reference for Azure Billing SDK for .NET
author: pallavit
ms.author: pallavit
ms.data: 01/13/2023
ms.topic: reference
ms.devlang: dotnet
ms.service: billing
ms.date: 10/19/2017
---
# Azure Billing libraries for .NET

## Overview

Azure Billing API (preview) provides programmatic access to your Azure billing information and invoices.

## Management library

Install the [NuGet package](https://www.nuget.org/packages/Microsoft.Azure.Management.Billing) directly from the Visual Studio [Package Manager console][PackageManager] or with the [.NET Core CLI][DotNetCLI].

#### Visual Studio Package Manager

```powershell
Install-Package Microsoft.Azure.Management.Billing
```

```dotnetcli
dotnet add package Microsoft.Azure.Management.Billing
```

### Code Example

Connect to Azure and get a list of invoices.

```csharp
/* Include these directives
using Microsoft.Rest.Azure.Authentication;
using Microsoft.Azure.Management.Billing;
using Microsoft.Azure.Management.Billing.Models;
*/

// Log into Azure
var serviceCreds = ApplicationTokenProvider.LoginSilentAsync(tenantId, clientId, secret);
var billingClient = new BillingClient(serviceCreds);
billingClient.SubscriptionId = subscriptionId;

// Get list of invoices
billingClient.Invoices.List();
```

> [!div class="nextstepaction"]
> [Explore the management APIs](/dotnet/api/overview/azure/billing/management)

## Samples

* [Usage API](https://github.com/Azure-Samples/billing-dotnet-usage-api)
* [RateCard API](https://github.com/Azure-Samples/billing-dotnet-ratecard-api)
* [Multi-Tenant Web Application](https://github.com/Azure-Samples/billing-dotnet-webapp-multitenant)

[PackageManager]: https://docs.microsoft.com/nuget/tools/package-manager-console
[DotNetCLI]: https://docs.microsoft.com/dotnet/core/tools/dotnet-add-package