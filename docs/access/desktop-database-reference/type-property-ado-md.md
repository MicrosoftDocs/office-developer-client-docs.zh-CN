---
title: Type 属性 (ADO MD)
TOCTitle: Type property (ADO MD)
ms:assetid: 4aaa151e-1f02-aa7d-a9e5-e7019b200924
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249230(v=office.15)
ms:contentKeyID: 48544671
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3f5cffb5fb888298b23dad02d9593978e581aa6c
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25928745"
---
# <a name="type-property-ado-md"></a><span data-ttu-id="60017-102">Type 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="60017-102">Type property (ADO MD)</span></span>


<span data-ttu-id="60017-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="60017-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="60017-104">指示当前成员的类型。</span><span class="sxs-lookup"><span data-stu-id="60017-104">Indicates the type of the current member.</span></span>

## <a name="return-values"></a><span data-ttu-id="60017-105">返回值</span><span class="sxs-lookup"><span data-stu-id="60017-105">Return values</span></span>

<span data-ttu-id="60017-106">返回一个 [MemberTypeEnum](membertypeenum.md) 值，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="60017-106">Returns a [MemberTypeEnum](membertypeenum.md) value and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="60017-107">备注</span><span class="sxs-lookup"><span data-stu-id="60017-107">Remarks</span></span>

<span data-ttu-id="60017-p101">此属性仅在 [Level](member-object-ado-md.md) 对象所属的 [Member](level-object-ado-md.md) 对象上受支持。从 **Position** 对象所属的 [Member](position-object-ado-md.md) 对象引用此属性时，会发生错误。</span><span class="sxs-lookup"><span data-stu-id="60017-p101">This property is supported only on [Member](member-object-ado-md.md) objects belonging to a [Level](level-object-ado-md.md) object. An error occurs when this property is referenced from **Member** objects belonging to a [Position](position-object-ado-md.md) object.</span></span>

