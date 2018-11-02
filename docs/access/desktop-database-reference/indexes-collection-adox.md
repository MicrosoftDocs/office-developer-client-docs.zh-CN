---
title: Indexes 集合 (ADOX)
TOCTitle: Indexes collection (ADOX)
ms:assetid: ab04bdd1-7c4a-44cb-dfc6-add3a52f502f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249793(v=office.15)
ms:contentKeyID: 48546963
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7d40736d30b0ebb62796b7cd2d0f8b4ede9e964c
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25930649"
---
# <a name="indexes-collection-adox"></a><span data-ttu-id="065d3-102">Indexes 集合 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="065d3-102">Indexes collection (ADOX)</span></span>


<span data-ttu-id="065d3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="065d3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="065d3-104">包含表的所有 [Index](index-object-adox.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="065d3-104">Contains all [Index](index-object-adox.md) objects of a table.</span></span>

## <a name="remarks"></a><span data-ttu-id="065d3-105">说明</span><span class="sxs-lookup"><span data-stu-id="065d3-105">Remarks</span></span>

<span data-ttu-id="065d3-p101">[Indexes](append-method-adox-indexes.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="065d3-p101">The [Append](append-method-adox-indexes.md) method for an **Indexes** collection is unique for ADOX. You can:</span></span>

  - <span data-ttu-id="065d3-108">使用 **Append** 方法向集合添加新索引。</span><span class="sxs-lookup"><span data-stu-id="065d3-108">Add a new index to the collection with the **Append** method.</span></span>

<span data-ttu-id="065d3-p102">其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="065d3-p102">The remaining properties and methods are standard to ADO collections. You can:</span></span>

  - <span data-ttu-id="065d3-111">使用 [Item](item-property-ado.md) 属性访问集合中的索引。</span><span class="sxs-lookup"><span data-stu-id="065d3-111">Access an index in the collection with the [Item](item-property-ado.md) property.</span></span>

  - <span data-ttu-id="065d3-112">使用 [Count](count-property-ado.md) 属性返回集合中包含的索引数。</span><span class="sxs-lookup"><span data-stu-id="065d3-112">Return the number of indexes contained in the collection with the [Count](count-property-ado.md) property.</span></span>

  - <span data-ttu-id="065d3-113">使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除索引。</span><span class="sxs-lookup"><span data-stu-id="065d3-113">Remove an index from the collection with the [Delete](delete-method-adox-collections.md) method.</span></span>

  - <span data-ttu-id="065d3-114">使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="065d3-114">Update the objects in the collection to reflect the current database's schema with the [Refresh](refresh-method-ado.md) method.</span></span>

