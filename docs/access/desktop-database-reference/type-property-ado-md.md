---
title: Type 属性 (ADO MD)
TOCTitle: Type property (ADO MD)
ms:assetid: 4aaa151e-1f02-aa7d-a9e5-e7019b200924
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249230(v=office.15)
ms:contentKeyID: 48544671
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 99b4e3e2c6930d8162c57d75978e9dba7b5af3e7
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721925"
---
# <a name="type-property-ado-md"></a><span data-ttu-id="ee8ca-102">Type 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="ee8ca-102">Type property (ADO MD)</span></span>


<span data-ttu-id="ee8ca-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ee8ca-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ee8ca-104">指示当前成员的类型。</span><span class="sxs-lookup"><span data-stu-id="ee8ca-104">Indicates the type of the current member.</span></span>

## <a name="return-values"></a><span data-ttu-id="ee8ca-105">返回值</span><span class="sxs-lookup"><span data-stu-id="ee8ca-105">Return values</span></span>

<span data-ttu-id="ee8ca-106">返回一个 [MemberTypeEnum](membertypeenum.md) 值，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="ee8ca-106">Returns a [MemberTypeEnum](membertypeenum.md) value and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee8ca-107">备注</span><span class="sxs-lookup"><span data-stu-id="ee8ca-107">Remarks</span></span>

<span data-ttu-id="ee8ca-p101">此属性仅在 [Level](member-object-ado-md.md) 对象所属的 [Member](level-object-ado-md.md) 对象上受支持。从 **Position** 对象所属的 [Member](position-object-ado-md.md) 对象引用此属性时，会发生错误。</span><span class="sxs-lookup"><span data-stu-id="ee8ca-p101">This property is supported only on [Member](member-object-ado-md.md) objects belonging to a [Level](level-object-ado-md.md) object. An error occurs when this property is referenced from **Member** objects belonging to a [Position](position-object-ado-md.md) object.</span></span>

