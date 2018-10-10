---
title: Index 对象 (ADOX)
TOCTitle: Index Object (ADOX)
ms:assetid: fe368ab1-e396-4684-d930-18b0ba58a925
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250304(v=office.15)
ms:contentKeyID: 48548929
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 535ca6a597c6dd580146f6142731897600264526
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466931"
---
# <a name="index-object-adox"></a>Index 对象 (ADOX)

**适用于**： Access 2013 |Office 2013

代表数据库表中的索引。

## <a name="remarks"></a>说明

以下代码创建一个新的 **Index** ：

`Dim obj As New Index`

使用 **Index** 对象的属性和集合，可以执行下列操作：

  - 使用 [Name](name-property-adox.md) 属性标识索引。

  - 使用 [Columns](columns-collection-adox.md) 集合访问索引的数据库列。

  - 使用 [Unique](unique-property-adox.md) 属性指定索引键是否必须唯一。

  - 使用 [PrimaryKey](primarykey-property-adox.md) 属性指定索引是否为表的主键。

  - 使用 [IndexNulls](indexnulls-property-adox.md) 属性指定在其索引字段中具有空值的记录是否具有索引项。

  - 使用 [Clustered](clustered-property-adox.md) 属性指定索引是否为聚集索引。

  - 使用 [Properties](properties-collection-ado.md) 集合访问提供程序特定的索引属性。


> [!NOTE]
> [!注释] 如果追加到 [Tables](column-object-adox.md) 集合中的 **Table** 对象中没有 **Column**，则在将该 **Column** 追加到 [Index](table-object-adox.md) 的 [Columns](tables-collection-adox.md) 集合时将发生错误。

您的数据提供程序可能并不支持 **Index** 对象的所有属性。如果您设置了提供程序不支持的属性的值，将发生错误。对于新的 **Index** 对象，将其追加到集合时，将发生错误。对于现有对象，在设置属性时，将发生错误。

创建 **Index** 对象时，有的可选属性具有适当的默认值，但这并不保证您的提供程序支持该属性。有关您的提供程序支持哪些属性的详细信息，请参阅提供程序文档。

