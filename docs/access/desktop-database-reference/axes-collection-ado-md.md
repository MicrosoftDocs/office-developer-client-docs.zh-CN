---
title: Axes 集合 (ADO MD)
TOCTitle: Axes collection (ADO MD)
ms:assetid: 7c719197-45f1-a5b9-665d-25cb693b1eb0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249520(v=office.15)
ms:contentKeyID: 48545836
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c88bf27f406a439d051112afb9abf94697a13b12
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922228"
---
# <a name="axes-collection-ado-md"></a><span data-ttu-id="8a3a6-102">Axes 集合 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="8a3a6-102">Axes collection (ADO MD)</span></span>


<span data-ttu-id="8a3a6-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8a3a6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8a3a6-104">包含定义单元格集的 [Axis](axis-object-ado-md.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="8a3a6-104">Contains the [Axis](axis-object-ado-md.md) objects that define a cellset.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a3a6-105">说明</span><span class="sxs-lookup"><span data-stu-id="8a3a6-105">Remarks</span></span>

<span data-ttu-id="8a3a6-p101">[Cellset](cellset-object-ado-md.md) 对象包含 **Axes** 集合。一旦打开了 **Cellset** ，此集合将包含至少一个 **Axis** 。有关如何使用 [Axis](axis-object-ado-md.md) 对象的更详细说明，请参阅 **Axis** 对象。</span><span class="sxs-lookup"><span data-stu-id="8a3a6-p101">A [Cellset](cellset-object-ado-md.md) object contains an **Axes** collection. Once the **Cellset** is opened, this collection will contain at least one **Axis**. See the [Axis](axis-object-ado-md.md) object for a more detailed explanation of how to use **Axis** objects.</span></span>


> [!NOTE]
> <span data-ttu-id="8a3a6-p102">[!注释] **Cellset** 的筛选轴不包含在 **Axes** 集合中。有关详细信息，请参阅 [FilterAxis](filteraxis-property-ado-md.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="8a3a6-p102">The filter axis of a **Cellset** is not contained in the **Axes** collection. See the [FilterAxis](filteraxis-property-ado-md.md) property for more information.</span></span>



<span data-ttu-id="8a3a6-p103">**Axes** 是一个标准 ADO 集合。使用集合的属性和方法，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="8a3a6-p103">**Axes** is a standard ADO collection. With the properties and methods of a collection, you can do the following:</span></span>

  - <span data-ttu-id="8a3a6-113">使用 [Count](count-property-ado.md) 属性获取集合中的对象数。</span><span class="sxs-lookup"><span data-stu-id="8a3a6-113">Obtain the number of objects in the collection with the [Count](count-property-ado.md) property.</span></span>

  - <span data-ttu-id="8a3a6-114">使用默认的 [Item](item-property-ado.md) 属性返回集合中的某个对象。</span><span class="sxs-lookup"><span data-stu-id="8a3a6-114">Return an object from the collection with the default [Item](item-property-ado.md) property.</span></span>

  - <span data-ttu-id="8a3a6-115">使用 [Refresh](refresh-method-ado.md) 方法更新来自提供程序的集合中的对象。</span><span class="sxs-lookup"><span data-stu-id="8a3a6-115">Update the objects in the collection from the provider with the [Refresh](refresh-method-ado.md) method.</span></span>

