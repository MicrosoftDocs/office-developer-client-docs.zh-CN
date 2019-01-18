---
title: 将数据添加到 Recordset
TOCTitle: Adding data to a Recordset
ms:assetid: a3d121a8-f52f-66cd-8849-c3a75aeb276a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249761(v=office.15)
ms:contentKeyID: 48546797
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0d16eb5871bfe55af58a89cc06b413e8404df8cb
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28701394"
---
# <a name="adding-data-to-a-recordset"></a>将数据添加到 Recordset

**适用于**： Access 2013、 Office 2013

**Recordset** 可能是最常使用的 ADO 对象。在 ADO 中，最好将 **Recordset** 看作从数据源得到的结果集和与其关联的游标行为的组合。因此，可以将数据放在 **Recordset** 中，然后使用 **Recordset** 的方法和属性在数据行中导航，查看行中的值以及操作结果集。

这一节将重点介绍如何向 **Recordset** 添加数据。有关在数据中导航或更新数据的信息，请参阅 [第 4 章：编辑数据](chapter-4-editing-data.md)和[第 5 章：更新和持久化数据](chapter-5-updating-and-persisting-data.md)。完全不需要 **Command** 对象的高级功能，就能将结果设置添加到 **Recordset** 。通常，可以通过设置 **Recordset** 的 **Source** 属性或将命令字符串传递到 **Recordset** 对象的 **Open** 方法来执行命令。

可以用多种方式将数据源的数据添加到 **Recordset** ，所使用的技术取决于应用程序的需要和提供程序的功能。

