---
title: Columns 集合 (ADOX)
TOCTitle: Columns collection (ADOX)
ms:assetid: 231645db-70da-9ad1-fb27-02145ce32e66
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249008(v=office.15)
ms:contentKeyID: 48543723
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e8278e43ba04047225f54171782c6a745a579595
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922298"
---
# <a name="columns-collection-adox"></a><span data-ttu-id="3961c-102">Columns 集合 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="3961c-102">Columns collection (ADOX)</span></span>


<span data-ttu-id="3961c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3961c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3961c-104">包含表、索引或键的所有 [Column](column-object-adox.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="3961c-104">Contains all [Column](column-object-adox.md) objects of a table, index, or key.</span></span>

## <a name="remarks"></a><span data-ttu-id="3961c-105">说明</span><span class="sxs-lookup"><span data-stu-id="3961c-105">Remarks</span></span>

<span data-ttu-id="3961c-p101">[Columns](append-method-adox-columns.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="3961c-p101">The [Append](append-method-adox-columns.md) method for a **Columns** collection is unique for ADOX. You can:</span></span>

  - <span data-ttu-id="3961c-108">使用 **Append** 方法向集合添加新列。</span><span class="sxs-lookup"><span data-stu-id="3961c-108">Add a new column to the collection with the **Append** method.</span></span>

<span data-ttu-id="3961c-p102">其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="3961c-p102">The remaining properties and methods are standard to ADO collections. You can:</span></span>

  - <span data-ttu-id="3961c-111">使用 [Item](item-property-ado.md) 属性访问集合中的列。</span><span class="sxs-lookup"><span data-stu-id="3961c-111">Access a column in the collection with the [Item](item-property-ado.md) property.</span></span>

  - <span data-ttu-id="3961c-112">使用 [Count](count-property-ado.md) 属性返回集合中包含的列数。</span><span class="sxs-lookup"><span data-stu-id="3961c-112">Return the number of columns contained in the collection with the [Count](count-property-ado.md) property.</span></span>

  - <span data-ttu-id="3961c-113">使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除列。</span><span class="sxs-lookup"><span data-stu-id="3961c-113">Remove a column from the collection with the [Delete](delete-method-adox-collections.md) method.</span></span>

  - <span data-ttu-id="3961c-114">使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="3961c-114">Update the objects in the collection to reflect the current database's schema with the [Refresh](refresh-method-ado.md) method.</span></span>


> [!NOTE]
> <span data-ttu-id="3961c-115">[!注释] 如果追加到 **Tables** 集合中的 **Table** 中没有某个 [Column](index-object-adox.md) ，则在将该 **Column** 追加到 [Index](table-object-adox.md) 的 [Columns](tables-collection-adox.md) 集合时将发生错误。</span><span class="sxs-lookup"><span data-stu-id="3961c-115">An error will occur when appending a **Column** to the **Columns** collection of an [Index](index-object-adox.md) if the **Column** does not exist in a [Table](table-object-adox.md) that is already appended to the [Tables](tables-collection-adox.md) collection.</span></span>


