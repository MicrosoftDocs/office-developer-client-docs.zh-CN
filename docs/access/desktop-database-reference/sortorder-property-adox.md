---
title: SortOrder 属性 (ADOX)
TOCTitle: SortOrder property (ADOX)
ms:assetid: c2b8c84d-acc4-9929-fff5-9a088abbfcf1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249951(v=office.15)
ms:contentKeyID: 48547557
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 735e72e8ed4f06c887ff790209529787e38142a4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306438"
---
# <a name="sortorder-property-adox"></a>SortOrder 属性 (ADOX)


**适用于**：Access 2013、Office 2013

指示列的排序顺序（仅限索引列）。

## <a name="settings-and-return-values"></a>设置和返回值

设置和返回一个 **Long** 值，该值可为 [SortOrderEnum](sortorderenum.md) 常量之一。 默认值为 **adSortAscending**。

## <a name="remarks"></a>注解

此属性仅适用于 [Index](index-object-adox.md) 的 [Columns](columns-collection-adox.md) 集合中的 [Column](column-object-adox.md) 对象。

