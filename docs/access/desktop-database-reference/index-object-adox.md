---
title: Index 对象 (ADOX)
TOCTitle: Index object (ADOX)
ms:assetid: fe368ab1-e396-4684-d930-18b0ba58a925
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250304(v=office.15)
ms:contentKeyID: 48548929
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 02d12fffa2c766425054e344e9f7d9d7a22cb517
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699175"
---
# <a name="index-object-adox"></a><span data-ttu-id="02680-102">Index 对象 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="02680-102">Index object (ADOX)</span></span>

<span data-ttu-id="02680-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="02680-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="02680-104">代表数据库表中的索引。</span><span class="sxs-lookup"><span data-stu-id="02680-104">Represents an index from a database table.</span></span>

## <a name="remarks"></a><span data-ttu-id="02680-105">说明</span><span class="sxs-lookup"><span data-stu-id="02680-105">Remarks</span></span>

<span data-ttu-id="02680-106">以下代码创建一个新的 **Index** ：</span><span class="sxs-lookup"><span data-stu-id="02680-106">The following code creates a new **Index**:</span></span>

`Dim obj As New Index`

<span data-ttu-id="02680-107">使用 **Index** 对象的属性和集合，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="02680-107">With the properties and collections of an **Index** object, you can:</span></span>

- <span data-ttu-id="02680-108">使用 [Name](name-property-adox.md) 属性标识索引。</span><span class="sxs-lookup"><span data-stu-id="02680-108">Identify the index with the [Name](name-property-adox.md) property.</span></span>

- <span data-ttu-id="02680-109">使用 [Columns](columns-collection-adox.md) 集合访问索引的数据库列。</span><span class="sxs-lookup"><span data-stu-id="02680-109">Access the database columns of the index with the [Columns](columns-collection-adox.md) collection.</span></span>

- <span data-ttu-id="02680-110">使用 [Unique](unique-property-adox.md) 属性指定索引键是否必须唯一。</span><span class="sxs-lookup"><span data-stu-id="02680-110">Specify whether the index keys must be unique with the [Unique](unique-property-adox.md) property.</span></span>

- <span data-ttu-id="02680-111">使用 [PrimaryKey](primarykey-property-adox.md) 属性指定索引是否为表的主键。</span><span class="sxs-lookup"><span data-stu-id="02680-111">Specify whether the index is the primary key for a table with the [PrimaryKey](primarykey-property-adox.md) property.</span></span>

- <span data-ttu-id="02680-112">使用 [IndexNulls](indexnulls-property-adox.md) 属性指定在其索引字段中具有空值的记录是否具有索引项。</span><span class="sxs-lookup"><span data-stu-id="02680-112">Specify whether records that have null values in their index fields have index entries with the [IndexNulls](indexnulls-property-adox.md) property.</span></span>

- <span data-ttu-id="02680-113">使用 [Clustered](clustered-property-adox.md) 属性指定索引是否为聚集索引。</span><span class="sxs-lookup"><span data-stu-id="02680-113">Specify whether the index is clustered with the [Clustered](clustered-property-adox.md) property.</span></span>

- <span data-ttu-id="02680-114">使用 [Properties](properties-collection-ado.md) 集合访问提供程序特定的索引属性。</span><span class="sxs-lookup"><span data-stu-id="02680-114">Access provider-specific index properties with the [Properties](properties-collection-ado.md) collection.</span></span>


> [!NOTE]
> <span data-ttu-id="02680-115">[!注释] 如果追加到 [Tables](column-object-adox.md) 集合中的 **Table** 对象中没有 **Column**，则在将该 **Column** 追加到 [Index](table-object-adox.md) 的 [Columns](tables-collection-adox.md) 集合时将发生错误。</span><span class="sxs-lookup"><span data-stu-id="02680-115">An error will occur when appending a [Column](column-object-adox.md) to the **Columns** collection of an **Index** if the **Column** does not exist in a [Table](table-object-adox.md) object already appended to the [Tables](tables-collection-adox.md) collection.</span></span>

<span data-ttu-id="02680-p101">您的数据提供程序可能并不支持 **Index** 对象的所有属性。如果您设置了提供程序不支持的属性的值，将发生错误。对于新的 **Index** 对象，将其追加到集合时，将发生错误。对于现有对象，在设置属性时，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="02680-p101">Your data provider may not support all properties of **Index** objects. An error will occur if you have set a value for a property that is not supported by the provider. For new **Index** objects, the error will occur when the object is appended to the collection. For existing objects, the error will occur when setting the property.</span></span>

<span data-ttu-id="02680-p102">创建 **Index** 对象时，有的可选属性具有适当的默认值，但这并不保证您的提供程序支持该属性。有关您的提供程序支持哪些属性的详细信息，请参阅提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="02680-p102">When creating **Index** objects, the existence of an appropriate default value for an optional property does not guarantee that your provider supports the property. For more information about which properties your provider supports, see your provider documentation.</span></span>

