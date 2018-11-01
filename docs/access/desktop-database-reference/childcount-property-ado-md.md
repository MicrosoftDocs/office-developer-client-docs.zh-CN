---
title: ChildCount 属性 (ADO MD)
TOCTitle: ChildCount Property (ADO MD)
ms:assetid: ff1872f0-d5f6-174e-0473-7997a462ca81
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250309(v=office.15)
ms:contentKeyID: 48548956
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0ac5e65356e7ee66cda864bffc983ae1d394825b
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25879604"
---
# <a name="childcount-property-ado-md"></a><span data-ttu-id="58bc3-102">ChildCount 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="58bc3-102">ChildCount Property (ADO MD)</span></span>


<span data-ttu-id="58bc3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="58bc3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="58bc3-104">指示在层次结构中将当前 [Member](member-object-ado-md.md) 对象作为父级的成员的数量。</span><span class="sxs-lookup"><span data-stu-id="58bc3-104">Indicates the number of members for which the current [Member](member-object-ado-md.md) object is the parent in a hierarchy.</span></span>

## <a name="return-values"></a><span data-ttu-id="58bc3-105">返回值</span><span class="sxs-lookup"><span data-stu-id="58bc3-105">Return values</span></span>

<span data-ttu-id="58bc3-106">返回一个 **Long** 整数值，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="58bc3-106">Returns a **Long** integer and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="58bc3-107">说明</span><span class="sxs-lookup"><span data-stu-id="58bc3-107">Remarks</span></span>

<span data-ttu-id="58bc3-p101">使用 **ChildCount** 属性可返回某个 **Member** 大致拥有的子级的数量。通过 **Children** 属性可返回 [Member](children-property-ado-md.md) 的实际子级。</span><span class="sxs-lookup"><span data-stu-id="58bc3-p101">Use the **ChildCount** property to return an estimate of how many children a **Member** has. The actual children of a **Member** can be returned by the [Children](children-property-ado-md.md) property.</span></span>

<span data-ttu-id="58bc3-p102">对于 **Position** 对象中的 [Member](position-object-ado-md.md) 对象，返回的最大数值为 65536。如果实际子级数量超过 65536，则返回的值仍为 65536。因此应用程序应将 **ChildCount** 等于 65536 解释为子级数量大于或等于 65536。</span><span class="sxs-lookup"><span data-stu-id="58bc3-p102">For **Member** objects from a [Position](position-object-ado-md.md) object, the maximum number returned is 65536. If the actual number of children exceeds 65536, the value returned will still be 65536. Therefore, the application should interpret a **ChildCount** of 65536 as equal to or greater than 65536 children.</span></span>

<span data-ttu-id="58bc3-p103">对于 **Level** 对象中的 [Member](level-object-ado-md.md) 对象，请使用 [Children](count-property-ado.md) 集合的 ADO 集合 **Count** 属性来确定子级的准确数量。如果集合中的子级数量巨大，则确定子级准确数量的过程可能会很慢。</span><span class="sxs-lookup"><span data-stu-id="58bc3-p103">For **Member** objects from a [Level](level-object-ado-md.md) object, use the ADO collection [Count](count-property-ado.md) property on the **Children** collection to determine the exact number of children. Determining the exact number of children may be slow if the number of children in the collection is large.</span></span>

