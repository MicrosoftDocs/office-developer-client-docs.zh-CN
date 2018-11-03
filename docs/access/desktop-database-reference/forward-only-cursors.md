---
title: 仅向前型游标
TOCTitle: Forward-only cursors
ms:assetid: 27541bac-077b-bfe6-d9d8-713e4a945125
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249035(v=office.15)
ms:contentKeyID: 48543834
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e742e3a6903faf7ab817b79675b100d026e25885
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946760"
---
# <a name="forward-only-cursors"></a>仅向前型游标

**适用于**： Access 2013、 Office 2013

典型的默认游标类型称为仅向前型（或不可滚动）游标，它只能在结果集中向前移动。仅向前型游标不支持滚动（在结果集中向前和向后移动的能力）；它只支持从结果集的开头到末尾提取行。利用某些仅向前型游标（例如，SQL Server 游标库中的游标），当前用户所发出的（或其他用户提交的）、影响到结果集中的行的所有插入、更新和删除语句在提取这些行时都是可见的。但是，由于游标无法向后滚动，将无法通过游标看见在提取数据库中的行之后对这些行所做的更改。

在处理当前行的数据之后，仅向前型游标将释放用来存放该数据的资源。默认情况下，仅向前型游标是动态的，这意味着在处理当前行时将检测所有更改。这样可以更快的速度打开游标，并使结果集能够显示对基础表所做的更新。

虽然仅向前型游标不支持向后滚动，但应用程序可以通过关闭并重新打开游标来返回到结果集的开头。在处理少量数据时，这种方式十分有效。另外，应用程序可以一次性读取结果集，然后在本地缓存数据，再浏览本地数据缓存。

如果应用程序不需要在结果集中滚动，则仅向前型游标是以最少量开销来快速检索数据的最佳方式。使用 **adOpenForwardOnly** **CursorTypeEnum** 可以指示您要在 ADO 中使用仅向前型游标。

