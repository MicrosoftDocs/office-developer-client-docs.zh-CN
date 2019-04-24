---
title: Views 集合 (ADOX)
TOCTitle: Views collection (ADOX)
ms:assetid: 8d0f9517-4be1-be9c-d4cd-6d50cd5a8983
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249618(v=office.15)
ms:contentKeyID: 48546246
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 6ce9986d486eb76046216aabbce6352280042910
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32312129"
---
# <a name="views-collection-adox"></a><span data-ttu-id="9db2c-102">Views 集合 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="9db2c-102">Views collection (ADOX)</span></span>


<span data-ttu-id="9db2c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="9db2c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9db2c-104">包含目录的所有 [View](view-object-adox.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="9db2c-104">Contains all [View](view-object-adox.md) objects of a catalog.</span></span>

## <a name="remarks"></a><span data-ttu-id="9db2c-105">注解</span><span class="sxs-lookup"><span data-stu-id="9db2c-105">Remarks</span></span>

<span data-ttu-id="9db2c-p101">**Views** 集合的 [Append](append-method-adox-views.md) 方法对于 ADOX 来说是唯一的。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9db2c-p101">The [Append](append-method-adox-views.md) method for a **Views** collection is unique for ADOX. You can:</span></span>

  - <span data-ttu-id="9db2c-108">使用 **Append** 方法向集合添加新视图。</span><span class="sxs-lookup"><span data-stu-id="9db2c-108">Add a new view to the collection with the **Append** method.</span></span>

<span data-ttu-id="9db2c-p102">其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9db2c-p102">The remaining properties and methods are standard to ADO collections. You can:</span></span>

  - <span data-ttu-id="9db2c-111">使用 [Item](item-property-ado.md) 属性访问集合中的视图。</span><span class="sxs-lookup"><span data-stu-id="9db2c-111">Access a view in the collection with the [Item](item-property-ado.md) property.</span></span>

  - <span data-ttu-id="9db2c-112">使用 [Count](count-property-ado.md) 属性返回集合中包含的视图数。</span><span class="sxs-lookup"><span data-stu-id="9db2c-112">Return the number of views contained in the collection with the [Count](count-property-ado.md) property.</span></span>

  - <span data-ttu-id="9db2c-113">使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除视图。</span><span class="sxs-lookup"><span data-stu-id="9db2c-113">Remove a view from the collection with the [Delete](delete-method-adox-collections.md) method.</span></span>

  - <span data-ttu-id="9db2c-114">使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="9db2c-114">Update the objects in the collection to reflect the current database's schema with the [Refresh](refresh-method-ado.md) method.</span></span>

