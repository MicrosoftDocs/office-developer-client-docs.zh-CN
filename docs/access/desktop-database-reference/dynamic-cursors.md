---
title: 动态游标 （访问桌面数据库参考 （英文）
TOCTitle: Dynamic cursors
ms:assetid: ae599d86-6b89-6103-fda1-c899a6138e1d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249823(v=office.15)
ms:contentKeyID: 48547068
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 63c67e028eaa478a2d348bd7c4dc4e945b3256a6
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947152"
---
# <a name="dynamic-cursors"></a>动态游标


**适用于**： Access 2013、 Office 2013

动态游标可以检测对结果集中的行的所有更改，无论这些更改是从游标内部发生的，还是由游标外部的其他用户引起的。通过游标，所有用户发出的所有插入、更新和删除语句都是可见的。动态游标可以检测在游标打开之后对结果集中的行、顺序和值进行的任何更改。在游标外部所做的更新要等到这些更新被提交以后才是可见的（除非将游标事务隔离级别设置为"不提交"）。

例如，假设动态游标提取了两个行和另一个应用程序，然后更新这些行中的某一行并删除其他行。如果动态游标随后再提取这些行，它将找不到已删除的行，但对于已更新的行它将显示新的值。

如果应用程序必须检测到由其他用户进行的所有并发更新，则动态游标是个好的选择。使用 **adOpenDynamic** **CursorTypeEnum** 可以指示您希望在 ADO 中使用动态游标。

[仅向前型游标](forward-only-cursors.md) | [静态游标](static-cursors.md) | [键集游标](keyset-cursors.md)

