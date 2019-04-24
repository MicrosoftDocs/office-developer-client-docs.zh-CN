---
title: 使用 CacheSize (Access desktop database reference)
TOCTitle: Using CacheSize
ms:assetid: b1677a9f-f22f-9456-0d2a-1ef7cf81bbdf
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249846(v=office.15)
ms:contentKeyID: 48547148
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 94e84ad8c8a87a6537c1abefe12427ecad0c0187
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32312122"
---
# <a name="using-cachesize"></a>使用 CacheSize

**适用于**：Access 2013、Office 2013

使用 **CacheSize** 属性可以控制一次从提供程序检索到本地内存中的记录数。例如，如果 **CacheSize** 为 10，则在首次打开 **Recordset** 对象后，提供程序会将前 10 条记录检索到本地内存中。在 **Recordset** 对象中移动时，提供程序将从本地内存缓冲区中返回数据。在通过缓存中的最后一条记录后，提供程序将立即从数据源中将接下来的 10 条记录检索到缓存中。

> [!NOTE]
> [!注释] **CacheSize** 基于 **Maximum Open Rows** 提供程序特定的属性（位于 **Recordset** 对象的 **Properties** 集合中）。不能将 **CacheSize** 设置为大于 **Maximum Open Rows** 的值。若要修改提供程序可打开的行数，可设置 **Maximum Open Rows** 。

**Recordset** 的值可以在 **CacheSize** 对象生存期间进行调整，但更改此值将仅影响在随后对数据源进行检索后缓存中的记录数。仅更此属性值不会更改缓存中的当前内容。

如果要检索的记录数小于 **CacheSize** 指定的值，提供程序将返回剩下的记录，而不会发生错误。

不允许将 **CacheSize** 设置为零，因为这会返回错误。

从缓存中检索的记录不反映其他用户对源数据所做的并发更改。若要强制对所有缓存数据进行更新，请使用 [Resync](resync-method-ado.md) 方法。

如果 **CacheSize** 设置为大于 1 的值，且在检索记录后执行了删除操作，则 navigation 方法（[Move](move-method-ado.md)、[MoveFirst、MoveLast、MoveNext 和 MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)）可能会导航至已删除的记录。在最初的提取后，除非您尝试访问已删除的行中的数据值，否则随后的删除不会反映到数据缓存中。不过，将 **CacheSize** 设置 1 时就不会提取已删除的行，即可消除此问题。

