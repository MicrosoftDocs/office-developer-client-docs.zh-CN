---
title: 类型的游标 （访问桌面数据库参考 （英文）
TOCTitle: Types of Cursors
ms:assetid: 589f3755-3cf5-9470-bd66-8e8afa218fc5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249299(v=office.15)
ms:contentKeyID: 48544996
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 559d2ea0ccf1cb34e801d75657695f191ef7076b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466320"
---
# <a name="types-of-cursors"></a>游标的类型


**适用于**： Access 2013 |Office 2013

作为一般规则，应用程序应使用可提供必需的数据访问的最简单游标。除基本特征（仅向前、只读、静态、滚动、无缓冲）外的每个其他游标特征都要在客户端内存、网络负载或性能等方面付出相应的代价。在很多情况下，默认游标选项会生成比您的应用程序实际需要更加复杂的游标。

游标类型的选择取决于应用程序使用结果集的方式，还取决于几种设计考虑，包括结果集的大小、可能使用的数据百分比、对数据更改的敏感性以及应用程序性能需求。

作为其最基本的原则，游标选择取决于您是需要更改数据还是仅查看数据：

  - 如果只需要浏览结果集而不更改数据，请使用[仅向前型](forward-only-cursors.md)或[静态](static-cursors.md)游标。

  - 如果具有很大的结果集，而只需要选择少量行，请使用[键集](keyset-cursors.md)游标。

  - 如果要将结果集与所有并发用户进行的最近添加、更改和删除内容同步，请使用[动态](dynamic-cursors.md)游标。

尽管每种游标类型看似截然不同，但请记住，这些游标类型之间的差别并不是很大，它们只是大部分相同的特征和选项相互配搭的结果。

