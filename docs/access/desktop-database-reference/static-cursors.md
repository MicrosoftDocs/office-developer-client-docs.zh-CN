---
title: 静态游标 （访问桌面数据库参考 （英文）
TOCTitle: Static Cursors
ms:assetid: 1acf7fc5-fb12-e59e-f480-dde378a29c53
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248950(v=office.15)
ms:contentKeyID: 48543524
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f60bce47f76214d26f75d13dece5bc062fd4db61
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25889824"
---
# <a name="static-cursors"></a>静态游标


**适用于**： Access 2013、 Office 2013

静态游标总是显示结果集在首次打开游标时的样子。静态游标是只读或可读/写的（因具体实现而异），并提供向前和向后滚动。静态游标通常不检测在打开游标之后对结果集的成员、顺序或值进行的更改。静态游标可以检测它们自己的更新、删除和插入，尽管它们不需要这样做。

静态游标从不检测其他更新、删除和插入。例如，假设静态游标提取某行，另一个应用程序随后对该行进行更新。如果该应用程序从静态游标重新提取此行，尽管另一个应用程序已进行了更改，但该应用程序看到仍是未更改的值。所有类型的滚动均受支持，但提供程序可能支持书签，也可能不支持书签。

如果您的应用程序不需要检测对数据进行的更改，只是需要滚动，则静态游标是最佳选择。使用 **adOpenStatic** **CursorTypeEnum** 指示要在 ADO 中使用静态游标。

