---
title: Children 属性 (ADO MD)
TOCTitle: Children Property (ADO MD)
ms:assetid: 66eff203-68e5-a36d-eb2f-2e9faa80deb6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249400(v=office.15)
ms:contentKeyID: 48545352
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e126b203e2282f96070f1f3eb14a9b926c04f432
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466101"
---
# <a name="children-property-ado-md"></a><span data-ttu-id="b1bd9-102">Children 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="b1bd9-102">Children Property (ADO MD)</span></span>


<span data-ttu-id="b1bd9-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="b1bd9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="b1bd9-104">返回层次结构中将当前 [Member](members-collection-ado-md.md) 作为父级的 [Members](member-object-ado-md.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="b1bd9-104">Returns a [Members](members-collection-ado-md.md) collection for which the current [Member](member-object-ado-md.md) is the parent in the hierarchy.</span></span>

## <a name="return-values"></a><span data-ttu-id="b1bd9-105">返回值</span><span class="sxs-lookup"><span data-stu-id="b1bd9-105">Return Values</span></span>

<span data-ttu-id="b1bd9-106">返回一个 **Members** 集合，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="b1bd9-106">Returns a **Members** collection and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1bd9-107">说明</span><span class="sxs-lookup"><span data-stu-id="b1bd9-107">Remarks</span></span>

<span data-ttu-id="b1bd9-p101">**Children** 属性包含将当前 **Member** 作为层次结构父级的 **Members** 集合。叶级 **Member** 对象在该 **Members** 集合中没有子成员。此属性仅在属于 **Level** 对象的 [Member](level-object-ado-md.md) 对象上受支持。通过属于 **Position** 对象的 [Member](position-object-ado-md.md) 对象引用此属性时，会发生错误。</span><span class="sxs-lookup"><span data-stu-id="b1bd9-p101">The **Children** property contains a **Members** collection for which the current **Member** is the hierarchical parent. Leaf level **Member** objects have no child members in the **Members** collection. This property is only supported on **Member** objects belonging to a [Level](level-object-ado-md.md) object. An error occurs when this property is referenced from **Member** objects belonging to a [Position](position-object-ado-md.md) object.</span></span>

