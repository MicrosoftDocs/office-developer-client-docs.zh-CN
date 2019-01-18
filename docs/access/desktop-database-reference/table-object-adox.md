---
title: Table 对象 (ADOX)
TOCTitle: Table object (ADOX)
ms:assetid: 53a3e2f9-4ec0-8fed-d482-4f995921587b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249273(v=office.15)
ms:contentKeyID: 48544874
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 6475621d711881b0187031aa037c8284e155546d
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710438"
---
# <a name="table-object-adox"></a>Table 对象 (ADOX)

**适用于**： Access 2013、 Office 2013

代表包括列、索引和键的数据库表。

## <a name="remarks"></a>说明

以下代码创建一个新的 **Table** ：

`Dim obj As New Table`

使用 **Table** 对象的属性和集合，可以执行下列操作：

- 使用 [Name](name-property-adox.md) 属性标识表。

- 使用 [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-tableadox) 属性确定表的类型。

- 使用 [Columns](columns-collection-adox.md) 集合访问表的数据库列。

- 使用 [Indexes](indexes-collection-adox.md) 集合访问表的索引。

- 使用 [Keys](keys-collection-adox.md) 集合访问表的键。

- 使用 [ParentCatalog](catalog-object-adox.md) 属性指定拥有表的 [Catalog](parentcatalog-property-adox.md)。

- 使用 [DateCreated](datecreated-property-adox.md) 和 [DateModified](datemodified-property-adox.md) 属性返回日期信息。

- 使用 [Properties](properties-collection-ado.md) 集合访问提供程序特定的表属性。


> [!NOTE]
> [!注释] 您的数据提供程序可能并不支持 **Table** 对象的所有属性。如果您设置了提供程序不支持的属性的值，将发生错误。对于新的 **Table** 对象，将其追加到集合时，将发生错误。对于现有对象，在设置属性时，将发生错误。

创建 **Table** 对象时，有的可选属性具有适当的默认值，但这并不保证您的提供程序支持该属性。有关您的提供程序支持哪些属性的详细信息，请参阅提供程序文档。

