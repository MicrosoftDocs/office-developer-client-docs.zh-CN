---
title: 使用 Microsoft Access 自动操作
TOCTitle: Automation with Microsoft Access
description: Microsoft Access 是一个支持自动化的 COM 组件，以前称为“OLE 自动化”。
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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296960"
---
# <a name="automation-with-microsoft-access"></a>使用 Microsoft Access 自动操作

**适用于**：Access 2013、Office 2013

Microsoft Access 是一种支持自动化功能的 COM 组件（以前，自动化称为“OLE 自动化”）。Microsoft Access 以两种方式支持“自动化”。可以从 Microsoft Access 中使用由其他组件所提供的对象，Microsoft Access 也可以将自己的对象提供给其他 COM 组件。

可以使用 **New** 关键字或 **CreateObject** 方法来创建组件的新实例。 可以使用 **GetObject** 方法将变量分配给组件的现有实例。

在 Microsoft Access 中通过“自动化”功能使用其他组件时，可以通过设置对组件类型库的引用来改善性能。Microsoft Access 还包含对象浏览器工具，可用于查看其他组件的类型库中的对象以及它们的方法和属性。

Microsoft Access 类型库向其他组件提供有关 Microsoft Access 对象的信息。 可以从某个组件对 Microsoft Access 类型库[设置引用](https://docs.microsoft.com/office/vba/access/Concepts/Settings/set-references-to-type-libraries)，并在“对象浏览器”中查看其对象。

要通过“自动化”来处理 Microsoft Access 对象，必须创建 Microsoft Access **[Application](https://docs.microsoft.com/office/vba/api/Access.Application)** 对象的实例。 例如，假设要在 Microsoft Access 窗体或报表中显示来自 Microsoft Excel 的数据。 为了从 Microsoft Excel 中启动 Microsoft Access，可以使用关键字 **New** 创建 Microsoft Access **Application** 对象的实例。 您也可以使用 **CreateObject** 方法新建 Microsoft Access **Application** 对象的实例，或者还可以使用 **GetObject** 方法将对象变量指向已有的 Microsoft Access 实例。 请查阅组件文档，以确定它支持何种语法。

启动 Microsoft Access 的实例之后，要想控制任何 Microsoft Access 对象，都必须使用数据库的 **[OpenCurrentDatabase](https://docs.microsoft.com/office/vba/api/Access.Application.OpenCurrentDatabase)** 方法或 **[NewCurrentDatabase](https://docs.microsoft.com/office/vba/api/Access.Application.NewCurrentDatabase)** 方法，或使用项目的 **[OpenAccessProject](https://docs.microsoft.com/office/vba/api/Access.Application.OpenAccessProject)** 或 **[NewAccessProject](https://docs.microsoft.com/office/vba/api/Access.Application.NewAccessProject)** 方法，在 Microsoft Access 窗口中打开数据库或项目 (.adp)。

如果你为了使用 Microsoft DAO 提供的数据访问对象而已经打开了 Microsoft Access，则不需要在 Microsoft Access 窗口中打开数据库。 在“自动化”操作期间，你可以使用 Microsoft Access **Application** 对象的 **[DBEngine](https://docs.microsoft.com/office/vba/api/Access.Application.DBEngine)** 属性来访问 Microsoft Office 12.0 Access Database Engine Object Library 中的对象。

