---
title: Append 方法（ADOX 列）
TOCTitle: Append method (ADOX Columns)
ms:assetid: e256a478-abc0-f15b-fc29-1b52e354144a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250152(v=office.15)
ms:contentKeyID: 48548285
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 48bc100b7b56265a570ce963b80f569f1d827150
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297121"
---
# <a name="append-method-adox-columns"></a>Append 方法（ADOX 列）

**适用于**：Access 2013、Office 2013

将新的 [Column](column-object-adox.md) 对象添加到 [Columns](columns-collection-adox.md) 集合。

## <a name="syntax"></a>语法

*列*。 Append*列* \[、*类型*\] \[*DefinedSize*\]

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Column* |要追加的 **Column** 对象，或者要创建并追加的列的名称。|
|*Type* |可选。指定该列的数据类型的 **Long** 值。*Type* 参数对应于 **Column** 对象的 [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-columnadox) 属性。|
|*DefinedSize* |可选。 指定该列的大小的 **Long** 值。 *DefinedSize* 参数对应于 **Column** 对象的 [DefinedSize](definedsize-property-adox.md) 属性。|


> [!NOTE]
> 如果追加到 [Tables](tables-collection-adox.md) 集合中的 [Table](table-object-adox.md) 中没有某个 **Column**，则在将该 **Column** 追加到 [Index](index-object-adox.md) 的 **Columns** 集合时将发生错误。


