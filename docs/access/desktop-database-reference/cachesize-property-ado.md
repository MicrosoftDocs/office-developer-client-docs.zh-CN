---
title: CacheSize 属性 (ADO)
TOCTitle: CacheSize property (ADO)
ms:assetid: 42f86cc0-30dc-669b-9e65-5e7ecd52c4d7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249200(v=office.15)
ms:contentKeyID: 48544491
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 725c2f81b3f3bce05a3007c50705e9cf35f7008f
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705825"
---
# <a name="cachesize-property-ado"></a>CacheSize 属性 (ADO)


**适用于**： Access 2013、 Office 2013

指示本地缓存在内存中的 [Recordset](recordset-object-ado.md) 对象的记录数。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个必须大于 0 的 **Long** 值。默认值为 1。

## <a name="remarks"></a>备注

使用 **CacheSize** 属性可以控制一次从提供程序检索到本地内存中的记录数。例如，如果 **CacheSize** 为 10，则在首次打开 **Recordset** 对象后，提供程序会将前 10 条记录检索到本地内存中。在 **Recordset** 对象中移动时，提供程序将从本地内存缓冲区中返回数据。在通过缓存中的最后一条记录后，提供程序将立即从数据源中将接下来的 10 条记录检索到缓存中。

> [!NOTE]
> [!注释] **CacheSize** 基于提供程序特定的属性 **Maximum Open Rows** （在 **Recordset** 对象的 **Properties** 集合中）。不能将 **CacheSize** 设置为大于 **Maximum Open Rows** 的值。若要修改提供程序可以打开的行数，请设置 **Maximum Open Rows** 。

**CacheSize** 的值可以在 **Recordset** 对象生存期间进行调整，但更改此值将仅影响在随后对数据源进行检索后缓存中的记录数。仅更此属性值不会更改缓存中的当前内容。

如果要检索的记录数小于 **CacheSize** 指定的值，提供程序将返回剩下的记录，而不会发生错误。

不允许将 **CacheSize** 设置为零，因为这会返回错误。

从缓存中检索的记录并不能反映其他用户对数据源所做的并发更改。若要强制更新所有已缓存的数据，请使用 [Resync](resync-method-ado.md) 方法。

如果 **CacheSize** 设置为大于 1  的值，并且在检索了记录后进行了删除操作，导航方法（[Move](move-method-ado.md)、[MoveFirst、MoveLast、MoveNext 和 MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)）可能会导致导航到已经删除的记录。进行了初始提取后，除非尝试访问已删除行中的数据，否则提取后发生的删除不会在数据缓存中得到反映。不过，将 **CacheSize** 设置为 1 就可以解决此问题，因为无法提取已删除的行。

