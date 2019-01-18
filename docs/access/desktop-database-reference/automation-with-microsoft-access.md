---
title: Microsoft Access 的“自动化”功能
TOCTitle: Automation with Microsoft Access
description: Microsoft Access 是支持自动化，以前称作 OLE 自动化的 COM 组件。
ms:assetid: 39fde349-3ba3-7c7a-3c92-316641dc8712
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192643(v=office.15)
ms:contentKeyID: 48544258
ms.date: 10/16/2018
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm13783
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 9635cdb2a06f610f42e4aa9fc9f998719aebb986
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716024"
---
# <a name="automation-with-microsoft-access"></a>使用 Microsoft Access 自动操作

**适用于**： Access 2013、 Office 2013

Microsoft Access 是一种支持自动化功能的 COM 组件（以前，自动化称为“OLE 自动化”）。Microsoft Access 以两种方式支持“自动化”。可以从 Microsoft Access 中使用由其他组件所提供的对象，Microsoft Access 也可以将自己的对象提供给其他 COM 组件。

您可以使用**New**关键字或**CreateObject**方法创建一个组件的新实例。 **GetObject**方法可用于将变量分配给组件的现有实例。

在 Microsoft Access 中通过“自动化”功能使用其他组件时，可以通过设置对组件类型库的引用来改善性能。Microsoft Access 还包含对象浏览器工具，可用于查看其他组件的类型库中的对象以及它们的方法和属性。

在 Microsoft Access 类型库提供给其他组件的 Microsoft Access 对象的信息。 您可以向 Microsoft Access[设置对](https://docs.microsoft.com/office/vba/access/Concepts/Settings/set-references-to-type-libraries)类型库从组件并在对象浏览器中查看其对象。

若要使用通过自动化的 Microsoft Access 对象，必须创建 Microsoft Access**[应用程序](https://docs.microsoft.com/office/vba/api/Access.Application)** 对象的实例。 例如，假设您想要在 Microsoft Access 窗体或报表中显示 Microsoft Excel 中的数据。 若要启动从 Microsoft Excel 的 Microsoft Access，您可以使用**New**关键字创建 Microsoft Access**应用程序**对象的实例。 您还可以使用**CreateObject**方法创建的新实例的 Microsoft Access**应用程序**对象，或者您可以使用**GetObject**方法以指向 Microsoft Access 的现有实例的一个对象变量。 检查您的组件的文档，以确定它支持哪些语法。

已启动 Microsoft Access 的实例，如果您希望控制任何 Microsoft Access 对象后，您必须打开数据库或项目 (.adp) 在 Microsoft Access 窗口中使用**[OpenCurrentDatabase](https://docs.microsoft.com/office/vba/api/Access.Application.OpenCurrentDatabase)** 或**[NewCurrentDatabase](https://docs.microsoft.com/office/vba/api/Access.Application.NewCurrentDatabase)** 方法的数据库或项目使用**[OpenAccessProject](https://docs.microsoft.com/office/vba/api/Access.Application.OpenAccessProject)** 或**[NewAccessProject](https://docs.microsoft.com/office/vba/api/Access.Application.NewAccessProject)** 方法。

如果您已打开仅作为一种使用 Microsoft DAO 提供数据访问对象的 Microsoft Access，您无需在 Microsoft Access 窗口中打开数据库。 自动化操作期间，可以在 Microsoft Office 12.0 Access 数据库引擎对象库中使用 Microsoft Access**应用程序**对象的访问对象的**[DBEngine](https://docs.microsoft.com/office/vba/api/Access.Application.DBEngine)** 属性。

