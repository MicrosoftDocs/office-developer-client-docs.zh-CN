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
# <a name="table-object-adox"></a><span data-ttu-id="731ef-102">Table 对象 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="731ef-102">Table object (ADOX)</span></span>

<span data-ttu-id="731ef-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="731ef-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="731ef-104">代表包括列、索引和键的数据库表。</span><span class="sxs-lookup"><span data-stu-id="731ef-104">Represents a database table including columns, indexes, and keys.</span></span>

## <a name="remarks"></a><span data-ttu-id="731ef-105">说明</span><span class="sxs-lookup"><span data-stu-id="731ef-105">Remarks</span></span>

<span data-ttu-id="731ef-106">以下代码创建一个新的 **Table** ：</span><span class="sxs-lookup"><span data-stu-id="731ef-106">The following code creates a new **Table**:</span></span>

`Dim obj As New Table`

<span data-ttu-id="731ef-107">使用 **Table** 对象的属性和集合，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="731ef-107">With the properties and collections of a **Table** object, you can:</span></span>

- <span data-ttu-id="731ef-108">使用 [Name](name-property-adox.md) 属性标识表。</span><span class="sxs-lookup"><span data-stu-id="731ef-108">Identify the table with the [Name](name-property-adox.md) property.</span></span>

- <span data-ttu-id="731ef-109">使用 [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-tableadox) 属性确定表的类型。</span><span class="sxs-lookup"><span data-stu-id="731ef-109">Determine the type of table with the [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-tableadox) property.</span></span>

- <span data-ttu-id="731ef-110">使用 [Columns](columns-collection-adox.md) 集合访问表的数据库列。</span><span class="sxs-lookup"><span data-stu-id="731ef-110">Access the database columns of the table with the [Columns](columns-collection-adox.md) collection.</span></span>

- <span data-ttu-id="731ef-111">使用 [Indexes](indexes-collection-adox.md) 集合访问表的索引。</span><span class="sxs-lookup"><span data-stu-id="731ef-111">Access the indexes of the table with the [Indexes](indexes-collection-adox.md) collection.</span></span>

- <span data-ttu-id="731ef-112">使用 [Keys](keys-collection-adox.md) 集合访问表的键。</span><span class="sxs-lookup"><span data-stu-id="731ef-112">Access the keys of the table with the [Keys](keys-collection-adox.md) collection.</span></span>

- <span data-ttu-id="731ef-113">使用 [ParentCatalog](catalog-object-adox.md) 属性指定拥有表的 [Catalog](parentcatalog-property-adox.md)。</span><span class="sxs-lookup"><span data-stu-id="731ef-113">Specify the [Catalog](catalog-object-adox.md) that owns the table with the [ParentCatalog](parentcatalog-property-adox.md) property.</span></span>

- <span data-ttu-id="731ef-114">使用 [DateCreated](datecreated-property-adox.md) 和 [DateModified](datemodified-property-adox.md) 属性返回日期信息。</span><span class="sxs-lookup"><span data-stu-id="731ef-114">Return date information with the [DateCreated](datecreated-property-adox.md) and [DateModified](datemodified-property-adox.md) properties.</span></span>

- <span data-ttu-id="731ef-115">使用 [Properties](properties-collection-ado.md) 集合访问提供程序特定的表属性。</span><span class="sxs-lookup"><span data-stu-id="731ef-115">Access provider-specific table properties with the [Properties](properties-collection-ado.md) collection.</span></span>


> [!NOTE]
> <span data-ttu-id="731ef-p101">[!注释] 您的数据提供程序可能并不支持 **Table** 对象的所有属性。如果您设置了提供程序不支持的属性的值，将发生错误。对于新的 **Table** 对象，将其追加到集合时，将发生错误。对于现有对象，在设置属性时，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="731ef-p101">Your data provider may not support all properties of **Table** objects. An error will occur if you have set a value for a property that the provider does not support. For new **Table** objects, the error will occur when the object is appended to the collection. For existing objects, the error will occur when setting the property.</span></span>

<span data-ttu-id="731ef-p102">创建 **Table** 对象时，有的可选属性具有适当的默认值，但这并不保证您的提供程序支持该属性。有关您的提供程序支持哪些属性的详细信息，请参阅提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="731ef-p102">When creating **Table** objects, the existence of an appropriate default value for an optional property does not guarantee that your provider supports the property. For more information about which properties your provider supports, see your provider documentation.</span></span>

