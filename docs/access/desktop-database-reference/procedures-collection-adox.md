---
title: Procedures 集合 (ADOX)
TOCTitle: Procedures collection (ADOX)
ms:assetid: e1ca53ad-1213-b514-e015-e18c2ab15e23
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250150(v=office.15)
ms:contentKeyID: 48548267
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 6c7bded8a6d0e6f2a4907977f32c8c37301ab323
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721169"
---
# <a name="procedures-collection-adox"></a><span data-ttu-id="a6037-102">Procedures 集合 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="a6037-102">Procedures collection (ADOX)</span></span>


<span data-ttu-id="a6037-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a6037-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a6037-104">包含目录的所有 [Procedure](procedure-object-adox.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="a6037-104">Contains all [Procedure](procedure-object-adox.md) objects of a catalog.</span></span>

## <a name="remarks"></a><span data-ttu-id="a6037-105">说明</span><span class="sxs-lookup"><span data-stu-id="a6037-105">Remarks</span></span>

<span data-ttu-id="a6037-p101">[Procedures](append-method-adox-procedures.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a6037-p101">The [Append](append-method-adox-procedures.md) method for a **Procedures** collection is unique for ADOX. You can:</span></span>

  - <span data-ttu-id="a6037-108">使用 **Append** 方法向集合添加新过程。</span><span class="sxs-lookup"><span data-stu-id="a6037-108">Add a new procedure to the collection with the **Append** method.</span></span>

<span data-ttu-id="a6037-p102">其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a6037-p102">The remaining properties and methods are standard to ADO collections. You can:</span></span>

  - <span data-ttu-id="a6037-111">使用 [Item](item-property-ado.md) 属性访问集合中的过程。</span><span class="sxs-lookup"><span data-stu-id="a6037-111">Access a procedure in the collection with the [Item](item-property-ado.md) property.</span></span>

  - <span data-ttu-id="a6037-112">使用 [Count](count-property-ado.md) 属性返回集合中包含的过程数。</span><span class="sxs-lookup"><span data-stu-id="a6037-112">Return the number of procedures contained in the collection with the [Count](count-property-ado.md) property.</span></span>

  - <span data-ttu-id="a6037-113">使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除过程。</span><span class="sxs-lookup"><span data-stu-id="a6037-113">Remove a procedure from the collection with the [Delete](delete-method-adox-collections.md) method.</span></span>

  - <span data-ttu-id="a6037-114">使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="a6037-114">Update the objects in the collection to reflect the current database's schema with the [Refresh](refresh-method-ado.md) method.</span></span>

