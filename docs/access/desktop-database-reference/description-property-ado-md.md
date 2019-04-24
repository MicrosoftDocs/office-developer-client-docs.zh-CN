---
title: Description 属性 (ADO MD)
TOCTitle: Description property (ADO MD)
ms:assetid: 06d5e1d0-6ed7-fe14-3723-3790e225482a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248816(v=office.15)
ms:contentKeyID: 48543055
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0f74532693f1054dd9d187757af840a3a00b451f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293936"
---
# <a name="description-property-ado-md"></a><span data-ttu-id="56c56-102">Description 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="56c56-102">Description property (ADO MD)</span></span>


<span data-ttu-id="56c56-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="56c56-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="56c56-104">返回当前对象的文本说明。</span><span class="sxs-lookup"><span data-stu-id="56c56-104">Returns a text explanation of the current object.</span></span>

## <a name="return-values"></a><span data-ttu-id="56c56-105">返回值</span><span class="sxs-lookup"><span data-stu-id="56c56-105">Return values</span></span>

<span data-ttu-id="56c56-106">返回一个 **String** 值，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="56c56-106">Returns a **String** and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="56c56-107">注解</span><span class="sxs-lookup"><span data-stu-id="56c56-107">Remarks</span></span>

<span data-ttu-id="56c56-p101">对于 [Member](member-object-ado-md.md) 对象， **Description** 仅适用于度量和公式成员。对于所有其他类型的成员， **Description** 均返回空字符串 ("")。有关各种成员的更多信息，请参阅 [Type](type-property-ado-md.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="56c56-p101">For [Member](member-object-ado-md.md) objects, **Description** applies only to measure and formula members. **Description** returns an empty string ("") for all other types of members. For more information about the various types of members, see the [Type](type-property-ado-md.md) property.</span></span>

<span data-ttu-id="56c56-p102">此属性仅在 **Level** 对象所属的 [Member](level-object-ado-md.md) 对象上受支持。当从 **Position** 对象所属的 [Member](position-object-ado-md.md) 对象引用此属性时，会发生错误。</span><span class="sxs-lookup"><span data-stu-id="56c56-p102">This property is only supported on **Member** objects belonging to a [Level](level-object-ado-md.md) object. An error occurs when this property is referenced from **Member** objects belonging to a [Position](position-object-ado-md.md) object.</span></span>

