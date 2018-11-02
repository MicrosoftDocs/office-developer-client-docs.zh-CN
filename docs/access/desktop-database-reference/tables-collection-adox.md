---
title: Tables 集合 (ADOX)
TOCTitle: Tables collection (ADOX)
ms:assetid: 07bc0541-c528-1c25-c8c4-05736836eda3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248821(v=office.15)
ms:contentKeyID: 48543082
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f87863579588b586e851cd175548d62ea7a0b920
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919484"
---
# <a name="tables-collection-adox"></a><span data-ttu-id="052a0-102">Tables 集合 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="052a0-102">Tables collection (ADOX)</span></span>


<span data-ttu-id="052a0-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="052a0-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="052a0-104">包含目录的所有 [Table](table-object-adox.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="052a0-104">Contains all [Table](table-object-adox.md) objects of a catalog.</span></span>

## <a name="remarks"></a><span data-ttu-id="052a0-105">说明</span><span class="sxs-lookup"><span data-stu-id="052a0-105">Remarks</span></span>

<span data-ttu-id="052a0-p101">[Tables](append-method-adox-tables.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="052a0-p101">The [Append](append-method-adox-tables.md) method for a **Tables** collection is unique for ADOX. You can:</span></span>

  - <span data-ttu-id="052a0-108">使用 **Append** 方法向集合添加新表。</span><span class="sxs-lookup"><span data-stu-id="052a0-108">Add a new table to the collection with the **Append** method.</span></span>

<span data-ttu-id="052a0-p102">其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="052a0-p102">The remaining properties and methods are standard to ADO collections. You can:</span></span>

  - <span data-ttu-id="052a0-111">使用 [Item](item-property-ado.md) 属性访问集合中的表。</span><span class="sxs-lookup"><span data-stu-id="052a0-111">Access a table in the collection with the [Item](item-property-ado.md) property.</span></span>

  - <span data-ttu-id="052a0-112">使用 [Count](count-property-ado.md) 属性返回集合中包含的表数。</span><span class="sxs-lookup"><span data-stu-id="052a0-112">Return the number of tables contained in the collection with the [Count](count-property-ado.md) property.</span></span>

  - <span data-ttu-id="052a0-113">使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除表。</span><span class="sxs-lookup"><span data-stu-id="052a0-113">Remove a table from the collection with the [Delete](delete-method-adox-collections.md) method.</span></span>

  - <span data-ttu-id="052a0-114">使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="052a0-114">Update the objects in the collection to reflect the current database's schema with the [Refresh](refresh-method-ado.md) method.</span></span>

<span data-ttu-id="052a0-p103">某些提供程序可能返回 Tables 集合中的其他架构对象，例如视图。因此，一些 ADOX 集合可能包含对同一对象的引用。如果您删除一个集合中的对象，则另一个引用被删除对象的集合在调用 Refresh 方法之前，将不会反映所做的更改。例如，使用 OLE DB Provider for Microsoft Jet 时，随 Tables 集合返回视图。如果删除视图，则必须刷新 Tables 集合，该集合才会反映所做的更改。</span><span class="sxs-lookup"><span data-stu-id="052a0-p103">Some providers may return other schema objects, such as a View, in the Tables collection. Therefore, some ADOX collections may contain references to the same object. Should you delete the object from one collection, the change will not be visible in another collection that references the deleted object until the Refresh method is called on the collection. For example, with the OLE DB Provider for Microsoft Jet, Views are returned with the Tables collection. If you drop a View, you must Refresh the Tables collection before the collection will reflect the change.</span></span>

