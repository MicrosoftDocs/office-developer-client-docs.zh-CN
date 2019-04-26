---
title: Access 变更（Access 桌面数据库参考）
TOCTitle: Changes in Access
description: Access does not include support for Access Data Projects (ADPs). Access introduces a new application type that enables you to create a web-based Access app.
ms:assetid: 8dfc5fc9-a6a7-4a91-8e97-c3874e9b880f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ618413(v=office.15)
ms:contentKeyID: 49106417
ms.date: 10/16/2018
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: de2ff21598639b445f5ff84240b115704b484209
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296498"
---
# <a name="changes-in-access"></a>Access 变更

**适用于**：Access 2013 | Office 2013

Access does not include support for Access Data Projects (ADPs). Access introduces a new application type that enables you to create a web-based Access app. 借助此应用程序类型，可以创建基于 Web 的应用程序，在本地或云中使用 SQL Server 的强大功能。

在 SharePoint Server 上的 Access 应用中，当你在 Access 客户端中创建表、查询或数据宏，以便在 SQL Server 数据库中创建表、视图或触发器时，借助 Access 客户端，可以向连接到 SQL Server 的其他应用程序开放你的数据库。 This enables you to share your data or load data from other systems into your Access app.

With Office 365 and Access, you can build applications that reach your users without having to worry about deployment challenges, software installation issues, or operating system compatibilities. Build your app in one location and share it across the web with the power of SQL Azure and SQL Server.

[SQL Azure](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview), the cloud version of SQL Server, does not support features that Access Data Projects (ADPs) rely on to operate. To support ADPs on SQL Azure, Access would require significant changes.

鉴于这些原因，Access 不支持 ADP。 在本地环境中，ADP 一直是与 SQL Server 一起使用的理想工具，然而，在 Access 2000 中引入 ADP 后，发生了很大的变化。 用户现在希望其数据库可以在任何地方使用。

## <a name="adp-support-and-the-future"></a>ADP 支持和未来展望

ADPs continue to work in earlier versions of Access. You can continue to develop your ADP applications and we will continue to support earlier versions of Access under the standard [support lifecycle](https://support.microsoft.com/lifecycle/search). We will not update older versions of Access to support new versions of SQL Server or SQL Azure. Therefore, you may encounter issues if you use SQL Server 2012 or later versions with your ADP. ADPs will continue to support SQL 2008 R2 and earlier.

For the future, ADP developers can consider several different possibilities:

- **转换为 Access 应用**：借助 Access，可以将表导入新的 Access 应用，这将自动为你创建应用程序的窗体。 可以扩展 Access 为你创建的基本窗体的功能，用户可以在 Web 上使用你的应用程序。 Although some of the functionality that you use in ADPs may not be available now, expect Microsoft to continue to focus improvements in the product for this application type.

- **转换为链接的桌面数据库**：Access 继续支持创建 .accdb 文件格式的桌面数据库。 You can convert your application to the .accdb format, including all of your existing forms and reports, and leave the data in SQL Server. 可以使用链接表链接到 SQL Server 数据库，你的应用程序将继续针对相同数据运行。

- **创建混合应用程序**：如果你的应用程序较大，并且你不需要在同一时间转换全部内容，可以将数据导入 Access 应用并以 .accdb 文件形式链接到 SQL Server 数据库。 这样就可以逐步迁移、逐步向 Access 应用添加窗体和功能，在 Access 应用后台使用链接表将 .accdb 文件形式的客户端应用程序保存到 SQL Server 数据库。

- **升级到 .NET Framework**：根据应用程序的复杂程度，可能需要考虑移至 .NET Framework 等专业开发平台。 借助 SQL Server，可以更轻松地使用现有数据库基础结构和扩展应用程序功能，而无需大规模地重写代码。

## <a name="conclusion"></a>总结

Access is designed to connect databases with the cloud by building on SharePoint Server and SQL Server technologies and easily work with Office 365. Access is designed to help you quickly create and share data-driven business apps that help run your business.

## <a name="see-also"></a>另请参阅

- [Access 2013 中面向开发人员的新增功能](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/new-in-access-for-developers)


