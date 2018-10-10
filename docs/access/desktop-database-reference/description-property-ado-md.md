---
title: Description 属性 (ADO MD)
TOCTitle: Description Property (ADO MD)
ms:assetid: 06d5e1d0-6ed7-fe14-3723-3790e225482a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248816(v=office.15)
ms:contentKeyID: 48543055
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 29c6723d710fcf3a8114fb4460326d87261c3fc1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466228"
---
# <a name="description-property-ado-md"></a><span data-ttu-id="5cf42-102">Description 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="5cf42-102">Description Property (ADO MD)</span></span>


<span data-ttu-id="5cf42-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="5cf42-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="5cf42-104">返回当前对象的文本说明。</span><span class="sxs-lookup"><span data-stu-id="5cf42-104">Returns a text explanation of the current object.</span></span>

## <a name="return-values"></a><span data-ttu-id="5cf42-105">返回值</span><span class="sxs-lookup"><span data-stu-id="5cf42-105">Return Values</span></span>

<span data-ttu-id="5cf42-106">返回一个 **String** 值，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="5cf42-106">Returns a **String** and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="5cf42-107">备注</span><span class="sxs-lookup"><span data-stu-id="5cf42-107">Remarks</span></span>

<span data-ttu-id="5cf42-p101">对于 [Member](member-object-ado-md.md) 对象， **Description** 仅适用于度量和公式成员。对于所有其他类型的成员， **Description** 均返回空字符串 ("")。有关各种成员的更多信息，请参阅 [Type](type-property-ado-md.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="5cf42-p101">For [Member](member-object-ado-md.md) objects, **Description** applies only to measure and formula members. **Description** returns an empty string ("") for all other types of members. For more information about the various types of members, see the [Type](type-property-ado-md.md) property.</span></span>

<span data-ttu-id="5cf42-p102">此属性仅在 **Level** 对象所属的 [Member](level-object-ado-md.md) 对象上受支持。当从 **Position** 对象所属的 [Member](position-object-ado-md.md) 对象引用此属性时，会发生错误。</span><span class="sxs-lookup"><span data-stu-id="5cf42-p102">This property is only supported on **Member** objects belonging to a [Level](level-object-ado-md.md) object. An error occurs when this property is referenced from **Member** objects belonging to a [Position](position-object-ado-md.md) object.</span></span>

