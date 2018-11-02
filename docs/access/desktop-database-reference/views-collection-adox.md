---
title: Views 集合 (ADOX)
TOCTitle: Views collection (ADOX)
ms:assetid: 8d0f9517-4be1-be9c-d4cd-6d50cd5a8983
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249618(v=office.15)
ms:contentKeyID: 48546246
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 053faa15583809ef7dad0db33de01fa16dd37d44
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25930838"
---
# <a name="views-collection-adox"></a><span data-ttu-id="244e5-102">Views 集合 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="244e5-102">Views collection (ADOX)</span></span>


<span data-ttu-id="244e5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="244e5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="244e5-104">包含目录的所有 [View](view-object-adox.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="244e5-104">Contains all [View](view-object-adox.md) objects of a catalog.</span></span>

## <a name="remarks"></a><span data-ttu-id="244e5-105">说明</span><span class="sxs-lookup"><span data-stu-id="244e5-105">Remarks</span></span>

<span data-ttu-id="244e5-p101">[Views](append-method-adox-views.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="244e5-p101">The [Append](append-method-adox-views.md) method for a **Views** collection is unique for ADOX. You can:</span></span>

  - <span data-ttu-id="244e5-108">使用 **Append** 方法向集合添加新视图。</span><span class="sxs-lookup"><span data-stu-id="244e5-108">Add a new view to the collection with the **Append** method.</span></span>

<span data-ttu-id="244e5-p102">其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="244e5-p102">The remaining properties and methods are standard to ADO collections. You can:</span></span>

  - <span data-ttu-id="244e5-111">使用 [Item](item-property-ado.md) 属性访问集合中的视图。</span><span class="sxs-lookup"><span data-stu-id="244e5-111">Access a view in the collection with the [Item](item-property-ado.md) property.</span></span>

  - <span data-ttu-id="244e5-112">使用 [Count](count-property-ado.md) 属性返回集合中包含的视图数。</span><span class="sxs-lookup"><span data-stu-id="244e5-112">Return the number of views contained in the collection with the [Count](count-property-ado.md) property.</span></span>

  - <span data-ttu-id="244e5-113">使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除视图。</span><span class="sxs-lookup"><span data-stu-id="244e5-113">Remove a view from the collection with the [Delete](delete-method-adox-collections.md) method.</span></span>

  - <span data-ttu-id="244e5-114">使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="244e5-114">Update the objects in the collection to reflect the current database's schema with the [Refresh](refresh-method-ado.md) method.</span></span>

