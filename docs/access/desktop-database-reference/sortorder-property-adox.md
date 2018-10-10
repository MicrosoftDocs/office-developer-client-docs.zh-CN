---
title: SortOrder 属性 (ADOX)
TOCTitle: SortOrder Property (ADOX)
ms:assetid: c2b8c84d-acc4-9929-fff5-9a088abbfcf1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249951(v=office.15)
ms:contentKeyID: 48547557
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 56898fc20d1d06a7be6e237d5054d0b9f0907ea6
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466373"
---
# <a name="sortorder-property-adox"></a>SortOrder 属性 (ADOX)


**适用于**： Access 2013 |Office 2013

指示列的排序顺序（仅限索引列）。

## <a name="settings-and-return-values"></a>设置和返回值

设置和返回一个 **Long** 值，该值可为 [SortOrderEnum](sortorderenum.md) 常量之一。默认值为 **adSortAscending** 。

## <a name="remarks"></a>备注

此属性仅适用于 [Index](column-object-adox.md) 的 [Columns](columns-collection-adox.md) 集合中的 [Column](index-object-adox.md) 对象。

