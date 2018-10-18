---
title: Children 属性 (ADO MD)
TOCTitle: Children Property (ADO MD)
ms:assetid: 66eff203-68e5-a36d-eb2f-2e9faa80deb6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249400(v=office.15)
ms:contentKeyID: 48545352
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: dbbae74ce8ce22255e97403fc3906dd50f36b38b
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25605049"
---
# <a name="children-property-ado-md"></a><span data-ttu-id="c225e-102">Children 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="c225e-102">Children Property (ADO MD)</span></span>


<span data-ttu-id="c225e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c225e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c225e-104">返回层次结构中将当前 [Member](members-collection-ado-md.md) 作为父级的 [Members](member-object-ado-md.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="c225e-104">Returns a [Members](members-collection-ado-md.md) collection for which the current [Member](member-object-ado-md.md) is the parent in the hierarchy.</span></span>

<span data-ttu-id="c225e-105"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="c225e-105"><<<<<<< HEAD</span></span>
## <a name="return-values"></a><span data-ttu-id="c225e-106">返回值</span><span class="sxs-lookup"><span data-stu-id="c225e-106">Return Values</span></span>
=======
## <a name="return-values"></a><span data-ttu-id="c225e-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c225e-107">Return values</span></span>
>>>>>>> <span data-ttu-id="c225e-108">master</span><span class="sxs-lookup"><span data-stu-id="c225e-108">master</span></span>

<span data-ttu-id="c225e-109">返回一个 **Members** 集合，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="c225e-109">Returns a **Members** collection and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="c225e-110">说明</span><span class="sxs-lookup"><span data-stu-id="c225e-110">Remarks</span></span>

<span data-ttu-id="c225e-p101">**Children** 属性包含将当前 **Member** 作为层次结构父级的 **Members** 集合。叶级 **Member** 对象在该 **Members** 集合中没有子成员。此属性仅在属于 **Level** 对象的 [Member](level-object-ado-md.md) 对象上受支持。通过属于 **Position** 对象的 [Member](position-object-ado-md.md) 对象引用此属性时，会发生错误。</span><span class="sxs-lookup"><span data-stu-id="c225e-p101">The **Children** property contains a **Members** collection for which the current **Member** is the hierarchical parent. Leaf level **Member** objects have no child members in the **Members** collection. This property is only supported on **Member** objects belonging to a [Level](level-object-ado-md.md) object. An error occurs when this property is referenced from **Member** objects belonging to a [Position](position-object-ado-md.md) object.</span></span>

