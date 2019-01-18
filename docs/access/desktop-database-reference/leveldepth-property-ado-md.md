---
title: LevelDepth 属性 (ADO MD)
TOCTitle: LevelDepth property (ADO MD)
ms:assetid: ba680f1e-2731-ad6b-4cee-cd3d8d114788
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249894(v=office.15)
ms:contentKeyID: 48547366
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 664a21f8b642c8db27580993089268e5d7b6f4ae
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28708562"
---
# <a name="leveldepth-property-ado-md"></a><span data-ttu-id="2f025-102">LevelDepth 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="2f025-102">LevelDepth property (ADO MD)</span></span>


<span data-ttu-id="2f025-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2f025-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2f025-104">指示层次结构的根和某个成员之间的级数。</span><span class="sxs-lookup"><span data-stu-id="2f025-104">Indicates the number of levels between the root of the hierarchy and a member.</span></span>

## <a name="return-values"></a><span data-ttu-id="2f025-105">返回值</span><span class="sxs-lookup"><span data-stu-id="2f025-105">Return values</span></span>

<span data-ttu-id="2f025-106">返回一个 **Long** 整数值，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="2f025-106">Returns a **Long** integer, and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f025-107">说明</span><span class="sxs-lookup"><span data-stu-id="2f025-107">Remarks</span></span>

<span data-ttu-id="2f025-p101">使用 **LevelDepth** 属性可确定 [Member](member-object-ado-md.md) 对象与层次结构的根级别之间的距离。根级别的成员的 **LevelDepth** 为 0。该属性对应于 [Level](depth-property-ado-md.md) 对象的 [Depth](level-object-ado-md.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="2f025-p101">Use the **LevelDepth** property to determine the distance of the [Member](member-object-ado-md.md) object from the root level of the hierarchy. The **LevelDepth** of a member at the root level is 0. This corresponds to the [Depth](depth-property-ado-md.md) property of a [Level](level-object-ado-md.md) object.</span></span>

