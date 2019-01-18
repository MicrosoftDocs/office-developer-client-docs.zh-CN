---
title: 使用 CacheSize （访问桌面数据库参考 （英文）
TOCTitle: Using CacheSize
ms:assetid: b1677a9f-f22f-9456-0d2a-1ef7cf81bbdf
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249846(v=office.15)
ms:contentKeyID: 48547148
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 94e84ad8c8a87a6537c1abefe12427ecad0c0187
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718957"
---
# <a name="using-cachesize"></a><span data-ttu-id="53927-102">使用 CacheSize</span><span class="sxs-lookup"><span data-stu-id="53927-102">Using CacheSize</span></span>

<span data-ttu-id="53927-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="53927-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="53927-p101">使用 **CacheSize** 属性可以控制一次从提供程序检索到本地内存中的记录数。例如，如果 **CacheSize** 为 10，则在首次打开 **Recordset** 对象后，提供程序会将前 10 条记录检索到本地内存中。在 **Recordset** 对象中移动时，提供程序将从本地内存缓冲区中返回数据。在通过缓存中的最后一条记录后，提供程序将立即从数据源中将接下来的 10 条记录检索到缓存中。</span><span class="sxs-lookup"><span data-stu-id="53927-p101">Use the **CacheSize** property to control how many records to retrieve at one time into local memory from the provider. For example, if the **CacheSize** is 10, after first opening the **Recordset** object, the provider retrieves the first 10 records into local memory. As you move through the **Recordset** object, the provider returns the data from the local memory buffer. As soon as you move past the last record in the cache, the provider retrieves the next 10 records from the data source into the cache.</span></span>

> [!NOTE]
> <span data-ttu-id="53927-p102">[!注释] **CacheSize** 基于 **Maximum Open Rows** 提供程序特定的属性（位于 **Recordset** 对象的 **Properties** 集合中）。不能将 **CacheSize** 设置为大于 **Maximum Open Rows** 的值。若要修改提供程序可打开的行数，可设置 **Maximum Open Rows** 。</span><span class="sxs-lookup"><span data-stu-id="53927-p102">**CacheSize** is based on the **Maximum Open Rows** provider-specific property (in the **Properties** collection of the **Recordset** object). You cannot set **CacheSize** to a value greater than **Maximum Open Rows**. To modify the number of rows that can be opened by the provider, set **Maximum Open Rows**.</span></span>

<span data-ttu-id="53927-p103">**Recordset** 的值可以在 **CacheSize** 对象生存期间进行调整，但更改此值将仅影响在随后对数据源进行检索后缓存中的记录数。仅更此属性值不会更改缓存中的当前内容。</span><span class="sxs-lookup"><span data-stu-id="53927-p103">The value of **CacheSize** can be adjusted during the life of the **Recordset** object, but changing this value only affects the number of records in the cache after subsequent retrievals from the data source. Changing the property value alone will not change the current contents of the cache.</span></span>

<span data-ttu-id="53927-113">如果要检索的记录数小于 **CacheSize** 指定的值，提供程序将返回剩下的记录，而不会发生错误。</span><span class="sxs-lookup"><span data-stu-id="53927-113">If there are fewer records to retrieve than **CacheSize** specifies, the provider returns the remaining records and no error occurs.</span></span>

<span data-ttu-id="53927-114">不允许将 **CacheSize** 设置为零，因为这会返回错误。</span><span class="sxs-lookup"><span data-stu-id="53927-114">A **CacheSize** setting of zero is not allowed and returns an error.</span></span>

<span data-ttu-id="53927-p104">从缓存中检索的记录不反映其他用户对源数据所做的并发更改。若要强制对所有缓存数据进行更新，请使用 [Resync](resync-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="53927-p104">Records retrieved from the cache do not reflect concurrent changes that other users made to the source data. To force an update of all the cached data, use the [Resync](resync-method-ado.md) method.</span></span>

<span data-ttu-id="53927-p105">如果 **CacheSize** 设置为大于 1 的值，且在检索记录后执行了删除操作，则 navigation 方法（[Move](move-method-ado.md)、[MoveFirst、MoveLast、MoveNext 和 MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)）可能会导航至已删除的记录。在最初的提取后，除非您尝试访问已删除的行中的数据值，否则随后的删除不会反映到数据缓存中。不过，将 **CacheSize** 设置 1 时就不会提取已删除的行，即可消除此问题。</span><span class="sxs-lookup"><span data-stu-id="53927-p105">If **CacheSize** is set to a value greater than 1, the navigation methods ([Move](move-method-ado.md), [MoveFirst, MoveLast, MoveNext, and MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)) may result in navigation to a deleted record, if deletion occurs after the records were retrieved. After the initial fetch, subsequent deletions will not be reflected in your data cache until you attempt to access a data value from a deleted row. However, setting **CacheSize** to 1 eliminates this issue because deleted rows cannot be fetched.</span></span>

