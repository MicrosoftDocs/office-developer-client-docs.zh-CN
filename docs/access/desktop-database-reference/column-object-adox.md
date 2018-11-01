---
title: Column 对象 (ADOX)
TOCTitle: Column Object (ADOX)
ms:assetid: ad38c2df-f704-0599-4b7a-8556e430ba46
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249811(v=office.15)
ms:contentKeyID: 48547034
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 28ae0f69303db5569b97799d8a77ca66828e2035
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25879618"
---
# <a name="column-object-adox"></a><span data-ttu-id="7e61f-102">Column 对象 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="7e61f-102">Column Object (ADOX)</span></span>


<span data-ttu-id="7e61f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7e61f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7e61f-104">代表表、索引或键中的列。</span><span class="sxs-lookup"><span data-stu-id="7e61f-104">Represents a column from a table, index, or key.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e61f-105">说明</span><span class="sxs-lookup"><span data-stu-id="7e61f-105">Remarks</span></span>

<span data-ttu-id="7e61f-106">以下代码创建一个新的 **Column** ：</span><span class="sxs-lookup"><span data-stu-id="7e61f-106">The following code creates a new **Column**:</span></span>

`Dim obj As New Column`

<span data-ttu-id="7e61f-107">使用 **Column** 对象的属性和集合，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="7e61f-107">With the properties and collections of a **Column** object, you can:</span></span>

  - <span data-ttu-id="7e61f-108">使用 [Name](name-property-adox.md) 属性标识列。</span><span class="sxs-lookup"><span data-stu-id="7e61f-108">Identify the column with the [Name](name-property-adox.md) property.</span></span>

  - <span data-ttu-id="7e61f-109">使用 [Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\)) 属性指定列的数据类型。</span><span class="sxs-lookup"><span data-stu-id="7e61f-109">Specify the data type of the column with the [Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\)) property.</span></span>

  - <span data-ttu-id="7e61f-110">使用 [Attributes](attributes-property-adox.md) 属性确定列是否为定长，或者列是否可以包含空值。</span><span class="sxs-lookup"><span data-stu-id="7e61f-110">Determine if the column is fixed-length, or if it can contain null values with the [Attributes](attributes-property-adox.md) property.</span></span>

  - <span data-ttu-id="7e61f-111">使用 [DefinedSize](definedsize-property-adox.md) 属性指定列的最大大小。</span><span class="sxs-lookup"><span data-stu-id="7e61f-111">Specify the maximum size of the column with the [DefinedSize](definedsize-property-adox.md) property.</span></span>

  - <span data-ttu-id="7e61f-112">对于数值数据值，使用 [NumericScale](numericscale-property-adox.md) 属性指定小数位。</span><span class="sxs-lookup"><span data-stu-id="7e61f-112">For numeric data values, specify the scale with the [NumericScale](numericscale-property-adox.md) property.</span></span>

  - <span data-ttu-id="7e61f-113">对于数值数据值，使用 [Precision](precision-property-adox.md) 属性指定最大精度。</span><span class="sxs-lookup"><span data-stu-id="7e61f-113">For numeric data value, specify the maximum precision with the [Precision](precision-property-adox.md) property.</span></span>

  - <span data-ttu-id="7e61f-114">使用 [ParentCatalog](catalog-object-adox.md) 属性指定拥有列的 [Catalog](parentcatalog-property-adox.md)。</span><span class="sxs-lookup"><span data-stu-id="7e61f-114">Specify the [Catalog](catalog-object-adox.md) that owns the column with the [ParentCatalog](parentcatalog-property-adox.md) property.</span></span>

  - <span data-ttu-id="7e61f-115">对于键列，使用 [RelatedColumn](relatedcolumn-property-adox.md) 属性指定相关表中的相关列的名称。</span><span class="sxs-lookup"><span data-stu-id="7e61f-115">For key columns, specify the name of the related column in the related table with the [RelatedColumn](relatedcolumn-property-adox.md) property.</span></span>

  - <span data-ttu-id="7e61f-116">对于索引列，使用 [SortOrder](sortorder-property-adox.md) 属性指定排序次序为升序还是降序。</span><span class="sxs-lookup"><span data-stu-id="7e61f-116">For index columns, specify whether the sort order is ascending or descending with the [SortOrder](sortorder-property-adox.md) property.</span></span>

  - <span data-ttu-id="7e61f-117">使用 [Properties](properties-collection-ado.md) 集合访问提供程序特定的属性。</span><span class="sxs-lookup"><span data-stu-id="7e61f-117">Access provider-specific properties with the [Properties](properties-collection-ado.md) collection.</span></span>


> [!NOTE]
> <span data-ttu-id="7e61f-p101">[!注释] 您的数据提供程序可能并不支持 **Column** 对象的所有属性。如果您设置了提供程序不支持的属性的值，将发生错误。对于新的 **Column** 对象，将其追加到集合时，将发生错误。对于现有对象，在设置属性时，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="7e61f-p101">Not all properties of **Column** objects may be supported by your data provider. An error will occur if you have set a value for a property that the provider does not support. For new **Column** objects, the error will occur when the object is appended to the collection. For existing objects, the error will occur when setting the property.</span></span>
> 
> <span data-ttu-id="7e61f-p102">创建 **Column** 对象时，有的可选属性具有适当的默认值，但这并不保证您的提供程序支持该属性。有关您的提供程序支持哪些属性的详细信息，请参阅提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="7e61f-p102">When creating **Column** objects, the existence of an appropriate default value for an optional property does not guarantee that your provider supports the property. For more information about which properties your provider supports, see your provider documentation.</span></span>

