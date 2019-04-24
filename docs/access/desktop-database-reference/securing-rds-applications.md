---
title: 保护 RDS 应用程序
TOCTitle: Securing RDS Applications
ms:assetid: 15f41cbb-d6e0-aca8-9c3a-97516d82c302
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248922(v=office.15)
ms:contentKeyID: 48543423
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4a531c01750117ae7abbf87e5ba4cb23daf37851
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308776"
---
# <a name="securing-rds-applications"></a>保护 RDS 应用程序

**适用于**：Access 2013、Office 2013

## <a name="microsoft-internet-explorer-security-issues"></a>Microsoft Internet Explorer 安全问题

在 Microsoft Internet Explorer 中添加了新的安全增强功能后, 某些 ADO 和 RDS 对象将仅限于在 "安全" 模式环境中运行。 这需要您注意这些问题，包括不同区域、安全级别、限制性行为、不安全的操作和自定义安全设置。

有关这些问题的详细信息，请参阅 ActiveX 数据对象 (ADO) 技术文章中的“Microsoft Internet Explorer 中的 ADO 和 RDS 安全问题”。

## <a name="security-and-your-web-server"></a>安全性和 web 服务器

如果您在 Internet web 服务器上使用[rdsserver.datafactory](datafactory-object-rdsserver.md)对象, 请记住这样做会带来潜在的安全风险。 获得有效数据源名称 (DSN)、用户 ID 和密码信息的外部用户可以编写将任何查询发送到该数据源的页面。 如果您希望进一步限制对数据源的访问，一种选择是撤消注册并删除 **RDSServer.DataFactory** 对象 (msadcf.dll)，转而使用带硬代码查询的自定义业务对象。

有关使用 DataFactory 对象的安全隐患的详细信息, 请参阅[microsoft 安全网站](https://www.microsoft.com/en-us/security/default.aspx)上的 microsoft 安全公告 MS99-025 rdsserver.datafactory。

## <a name="client-impersonation-and-security"></a>客户端模拟和安全性

如果您的 IIS web 服务器的**密码身份验证**属性设置为 windows nt 质询/响应身份验证 (针对 windows nt 4.0) 或集成 windows 身份验证 (针对 windows 2000), 则业务对象将在客户端上调用安全上下文。 这是 RDS 1.5 中的新增功能，它允许通过 HTTP 进行客户端模拟。 在此模式下工作时, 登录到 web 服务器 (IIS) 不是匿名的, 而是使用客户端计算机在其下运行的用户 ID 和密码。 如果 ODBC DSN 设置为使用可信连接，那么对 SQL Server 等数据库的访问也发生在客户端的安全性上下文中。 But this only works if the database is on the same computer as the IIS; the client credentials cannot be carried over to yet another computer.

例如，客户 John Doe 要登录到客户端计算机，他的用户 ID 为"JohnD"，密码为"secret"。 他运行基于浏览器的应用程序，该应用程序需访问 **RDSServer.DataFactory** 对象，并通过在运行 IIS 的“MyServer”计算机上执行 SQL 查询来创建 [Recordset](recordset-object-ado.md)。 MyServer 是一个运行 Windows NT Server 4.0 的系统，它设置为使用 Windows NT 质询/响应验证，它的 ODBC DSN 的“使用可信连接”处于选中状态，该服务器还包含 SQL Server 数据源。 当在 web 服务器上收到请求时, 它会询问客户端的用户 ID 和密码。 因此, 该请求在 MyServer 上记录为来自 "JohnD"/"Secret", 而不是\_IUSER MyServer (这是在匿名密码身份验证打开时的默认值)。 同样，当登录 SQL Server 时，将使用“JohnD”/“Secret”。

因此，在没有明确提示用户输入登录到数据库所需的用户 ID 和密码信息的情况下，IIS Windows NT 口令/应答身份验证模式允许创建 HTML 页面。如果使用 IIS 基本身份验证，也要求使用该模式。

## <a name="password-authentication"></a>密码验证

RDS 可以与在以下三种密码身份验证模式中运行的 IIS web 服务器进行通信: 匿名、基本或 NT 质询/响应身份验证 (在 Windows 2000 中称为 "集成 windows 身份验证")。 这些设置定义 web 服务器如何控制其访问权限, 例如要求客户端计算机具有对 NT web 服务器的显式访问权限。

