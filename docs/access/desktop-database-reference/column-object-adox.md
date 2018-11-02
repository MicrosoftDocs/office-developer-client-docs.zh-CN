---
title: Column 对象 (ADOX)
TOCTitle: Column object (ADOX)
ms:assetid: ad38c2df-f704-0599-4b7a-8556e430ba46
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249811(v=office.15)
ms:contentKeyID: 48547034
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ac4416dce7d3f9fa52c4b948b1e8d3e0167c2751
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25930628"
---
# <a name="column-object-adox"></a>Column 对象 (ADOX)


**适用于**： Access 2013、 Office 2013

代表表、索引或键中的列。

## <a name="remarks"></a>说明

以下代码创建一个新的 **Column** ：

`Dim obj As New Column`

使用 **Column** 对象的属性和集合，可以执行下列操作：

  - 使用 [Name](name-property-adox.md) 属性标识列。

  - 使用 [Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\)) 属性指定列的数据类型。

  - 使用 [Attributes](attributes-property-adox.md) 属性确定列是否为定长，或者列是否可以包含空值。

  - 使用 [DefinedSize](definedsize-property-adox.md) 属性指定列的最大大小。

  - 对于数值数据值，使用 [NumericScale](numericscale-property-adox.md) 属性指定小数位。

  - 对于数值数据值，使用 [Precision](precision-property-adox.md) 属性指定最大精度。

  - 使用 [ParentCatalog](catalog-object-adox.md) 属性指定拥有列的 [Catalog](parentcatalog-property-adox.md)。

  - 对于键列，使用 [RelatedColumn](relatedcolumn-property-adox.md) 属性指定相关表中的相关列的名称。

  - 对于索引列，使用 [SortOrder](sortorder-property-adox.md) 属性指定排序次序为升序还是降序。

  - 使用 [Properties](properties-collection-ado.md) 集合访问提供程序特定的属性。


> [!NOTE]
> [!注释] 您的数据提供程序可能并不支持 **Column** 对象的所有属性。如果您设置了提供程序不支持的属性的值，将发生错误。对于新的 **Column** 对象，将其追加到集合时，将发生错误。对于现有对象，在设置属性时，将发生错误。
> 
> 创建 **Column** 对象时，有的可选属性具有适当的默认值，但这并不保证您的提供程序支持该属性。有关您的提供程序支持哪些属性的详细信息，请参阅提供程序文档。

