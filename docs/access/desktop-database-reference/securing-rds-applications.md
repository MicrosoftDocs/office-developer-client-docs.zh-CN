---
title: 保护 RDS 应用程序
TOCTitle: Securing RDS Applications
ms:assetid: 15f41cbb-d6e0-aca8-9c3a-97516d82c302
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248922(v=office.15)
ms:contentKeyID: 48543423
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4d7bc9ff4741ca9a6eccfb6ede3f569c18d0d20e
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606464"
---
# <a name="securing-rds-applications"></a>保护 RDS 应用程序

**适用于**： Access 2013 |Office 2013

## <a name="microsoft-internet-explorer-security-issues"></a>Microsoft Internet Explorer 安全问题

使用 Microsoft® Internet Explorer 中新增的安全增强功能，一些 ADO 和 RDS 对象会被限制为只能在"安全"模式环境中运行。这需要您注意这些问题，包括不同区域、安全级别、限制性行为、不安全的操作和自定义安全设置。

有关这些问题的详细信息，请参阅 ActiveX 数据对象 (ADO) 技术文章中的"Microsoft Internet Explorer 中的 ADO 和 RDS 安全问题"。

<<<<<<< 标头
## <a name="security-and-your-web-server"></a>安全性和 Web 服务器

如果在 Internet Web 服务器上使用 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象，请记住这会造成潜在的安全风险。获得有效数据源名称 (DSN)、用户 ID 和密码信息的外部用户可以编写将任何查询发送到该数据源的页面。如果您希望进一步限制对数据源的访问，一种选择是撤消注册并删除 **RDSServer.DataFactory** 对象 (msadcf.dll)，转而使用带硬代码查询的自定义业务对象。
=======
## <a name="security-and-your-web-server"></a>安全性和您的 web 服务器

如果您 Internet web 服务器上使用[RDSServer.DataFactory](datafactory-object-rdsserver.md)对象，请记住，否则会创建潜在的安全风险。 获得有效数据源名称 (DSN)、用户 ID 和密码信息的外部用户可以编写将任何查询发送到该数据源的页面。 如果您希望进一步限制对数据源的访问，一种选择是撤消注册并删除 **RDSServer.DataFactory** 对象 (msadcf.dll)，转而使用带硬代码查询的自定义业务对象。
>>>>>>> master

有关使用 RDSServer.DataFactory 对象的安全问题的详细信息，请参阅[Microsoft 安全网站](https://www.microsoft.com/en-us/security/default.aspx)上的 Microsoft 安全公告 MS99-025。

## <a name="client-impersonation-and-security"></a>客户端模拟和安全性

<<<<<<< 标头如果您的 IIS Web 服务器的**密码身份验证**属性设置为 Windows NT 质询/响应身份验证 （用于 Windows NT 4.0) 或集成 Windows 身份验证 （适用于 Windows 2000)，然后业务对象在客户端的安全性上下文下调用。 这是通过 HTTP 允许客户端模拟的 RDS 1.5 中的新功能。 在这种模式下工作时，登录到 Web 服务器 (IIS) 不是匿名，但使用的用户 ID 和客户端计算机运行下的密码。 如果 ODBC Dsn 设置以使用受信任连接，然后访问数据库，如 SQL Server，也不会在客户端的安全性上下文下。 但这仅适用于如果数据库是在 IIS 中; 在同一台计算机上客户端凭据无法转移到另一计算机。

<a name="for-example-a-client-john-doe-with-useridjohnd-and-passwordsecret-is-logged-on-to-a-client-computer-he-runs-a-browser-based-application-that-needs-to-access-the-rdsserverdatafactory-object-to-create-a-recordsetrecordset-object-adomd-by-executing-an-sql-query-on-the-myserver-computer-running-iis-myserver-a-system-running-windows-nt-server-40-is-set-up-to-use-windows-nt-challengeresponse-authentication-its-odbc-dsn-has-use-trusted-connection-selected-and-the-server-also-contains-the-sql-server-data-source-when-a-request-is-received-on-the-web-server-it-asks-the-client-for-the-user-id-and-password-thus-the-request-is-logged-on-myserver-as-coming-from-johndsecret-instead-of-iusermyserver-which-is-the-default-when-anonymous-password-authentication-is-on-similarly-when-logging-on-to-sql-server-johndsecret-is-used"></a>例如，客户 John Doe 要登录到客户端计算机，他的用户 ID 为"JohnD"，密码为"secret"。 他运行基于浏览器的应用程序，该应用程序需访问 **RDSServer.DataFactory** 对象，并通过在运行 IIS 的"MyServer"计算机上执行 SQL 查询来创建 [Recordset](recordset-object-ado.md)。 MyServer 是一个运行 Windows NT Server 4.0 的系统，它设置为使用 Windows NT 质询/响应验证，它的 ODBC DSN 的"使用可信连接"处于选中状态，该服务器还包含 SQL Server 数据源。 当在 Web 服务器上收到请求时，它会要求客户输入用户 ID 和密码。 因此，请求登录 MyServer 为来自"JohnD"/"Secret"而不是 IUSER\_MyServer （这是默认值，在匿名的密码身份验证时）。 同样，当登录 SQL Server 时，将使用"JohnD"/"Secret"。
=======
如果 IIS web 服务器的**密码身份验证**属性设置为 Windows NT 质询/响应身份验证 （用于 Windows NT 4.0) 或集成 Windows 身份验证 （用于 Windows 2000)，然后业务对象调用下的客户端安全性上下文。 这是通过 HTTP 允许客户端模拟的 RDS 1.5 中的新功能。 在这种模式下工作时，登录到 web 服务器 (IIS) 不是匿名，但使用的用户 ID 和客户端计算机运行下的密码。 如果 ODBC Dsn 设置以使用受信任连接，然后访问数据库，如 SQL Server，也不会在客户端的安全性上下文下。 但这仅适用于如果数据库是在 IIS 中; 在同一台计算机上客户端凭据无法转移到另一计算机。

例如，客户 John Doe 要登录到客户端计算机，他的用户 ID 为"JohnD"，密码为"secret"。 他运行基于浏览器的应用程序，该应用程序需访问 **RDSServer.DataFactory** 对象，并通过在运行 IIS 的"MyServer"计算机上执行 SQL 查询来创建 [Recordset](recordset-object-ado.md)。 MyServer 是一个运行 Windows NT Server 4.0 的系统，它设置为使用 Windows NT 质询/响应验证，它的 ODBC DSN 的"使用可信连接"处于选中状态，该服务器还包含 SQL Server 数据源。 Web 服务器上收到请求后，它要求客户端的用户 ID 和密码。 因此，请求登录 MyServer 为来自"JohnD"/"Secret"而不是 IUSER\_MyServer （这是默认值，在匿名的密码身份验证时）。 同样，当登录 SQL Server 时，将使用"JohnD"/"Secret"。
>>>>>>> master

因此，在没有明确提示用户输入登录到数据库所需的用户 ID 和密码信息的情况下，IIS Windows NT 口令/应答身份验证模式允许创建 HTML 页面。如果使用 IIS 基本身份验证，也要求使用该模式。

## <a name="password-authentication"></a>密码验证

<<<<<<< 标头 RDS 可以与任何一个三种的密码身份验证模式中运行的 IIS Web 服务器通信： 匿名、 基本，或 NT 质询/响应身份验证 （在 Windows 2000 中称为集成 Windows 身份验证）。 这些设置定义 Web 服务器如何通过它控制访问，如要求客户端计算机在 NT Web 服务器上有明确的访问权限。
=== RDS 可以相互任一的三个的密码身份验证模式中运行的 IIS web 服务器： 匿名、 基本，或 NT 质询/响应身份验证 （在 Windows 2000 中称为集成 Windows 身份验证）。 这些设置定义如何 web 服务器控件通过它，如要求客户端计算机的 NT web 服务器上拥有显式访问权限的访问。
>>>>>>> master

