---
title: SortOrder 属性 (ADOX)
TOCTitle: SortOrder Property (ADOX)
ms:assetid: c2b8c84d-acc4-9929-fff5-9a088abbfcf1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249951(v=office.15)
ms:contentKeyID: 48547557
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8e17e160213eb4766c1ace8ac8afd0356dcf6bb5
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25890013"
---
# <a name="sortorder-property-adox"></a><span data-ttu-id="95544-102">SortOrder 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="95544-102">SortOrder Property (ADOX)</span></span>


<span data-ttu-id="95544-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="95544-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="95544-104">指示列的排序顺序（仅限索引列）。</span><span class="sxs-lookup"><span data-stu-id="95544-104">Indicates the sort sequence for the column (index columns only).</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="95544-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="95544-105">Settings and return values</span></span>

<span data-ttu-id="95544-p101">设置和返回一个 **Long** 值，该值可为 [SortOrderEnum](sortorderenum.md) 常量之一。默认值为 **adSortAscending** 。</span><span class="sxs-lookup"><span data-stu-id="95544-p101">Sets and returns a **Long** value that can be one of the [SortOrderEnum](sortorderenum.md) constants. The default value is **adSortAscending**.</span></span>

## <a name="remarks"></a><span data-ttu-id="95544-108">备注</span><span class="sxs-lookup"><span data-stu-id="95544-108">Remarks</span></span>

<span data-ttu-id="95544-109">此属性仅适用于 [Index](column-object-adox.md) 的 [Columns](columns-collection-adox.md) 集合中的 [Column](index-object-adox.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="95544-109">This property only applies to [Column](column-object-adox.md) objects in the [Columns](columns-collection-adox.md) collection of an [Index](index-object-adox.md).</span></span>

