---
title: 在即时模式和批模式下使用 AddNew
TOCTitle: Using AddNew in Immediate and Batch Modes
ms:assetid: 1dc32284-9514-083d-ce56-58abbafa7bb7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248970(v=office.15)
ms:contentKeyID: 48543602
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a6cfe882c8ad1c07aabfae323a1467be753b462b
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25890958"
---
# <a name="using-addnew-in-immediate-and-batch-modes"></a>在即时模式和批模式下使用 AddNew


**适用于**： Access 2013、 Office 2013

**AddNew**方法的行为取决于**Recordset**对象以及是否传递*FieldList*和*Values*参数的更新模式。

在即时更新模式（在此模式中，只要调用 **Update** 方法，提供程序就会将更改写入基础数据源）中，不使用参数调用 **AddNew** 方法会将 **EditMode** 属性设置为 **adEditAdd**。提供程序在本地缓存所有字段值的更改。调用 **Update** 方法会将新记录张贴到数据库并将 **EditMode** 属性重新设置为 **adEditNone**。如果传递 *FieldList* 和 *Values* 参数，ADO 立即将新记录张贴到数据库（不再需要 **Update** 调用）；而 **EditMode** 属性值不会改变 (**adEditNone**)。

在批更新模式中，调用不带参数的 **AddNew** 方法会将 **EditMode** 属性设置为 **adEditAdd** 。 提供程序在本地缓存所有字段值的更改。 调用 **Update** 方法会将新记录添加到当前 **Recordset** 并将 **EditMode** 属性重新设置为 **adEditNone** ，但是在调用 **UpdateBatch** 方法之前，提供程序不会将更改张贴到基础数据库中。 如果传递*FieldList*和*Values*参数，ADO 将新记录发送到用于存储缓存; 中的提供程序您需要调用**UpdateBatch**方法发布到基础数据库的新记录。 有关 **Update** 和 **UpdateBatch** 的详细信息，请参阅 [第 5 章：更新和持久化数据](chapter-5-updating-and-persisting-data.md)。

