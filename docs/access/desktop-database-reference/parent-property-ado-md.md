---
title: Parent 属性 (ADO MD)
TOCTitle: Parent Property (ADO MD)
ms:assetid: 62649da7-d35f-f11f-674c-28ce95abaf20
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249370(v=office.15)
ms:contentKeyID: 48545238
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7beba341a2374e1868c67c8f7b4fab73c71c0ba8
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25880297"
---
# <a name="parent-property-ado-md"></a><span data-ttu-id="882a0-102">Parent 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="882a0-102">Parent Property (ADO MD)</span></span>


<span data-ttu-id="882a0-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="882a0-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="882a0-104">指示层次结构中作为当前成员的父级的成员。</span><span class="sxs-lookup"><span data-stu-id="882a0-104">Indicates the member that is the parent of the current member in a hierarchy.</span></span>

## <a name="return-values"></a><span data-ttu-id="882a0-105">返回值</span><span class="sxs-lookup"><span data-stu-id="882a0-105">Return values</span></span>

<span data-ttu-id="882a0-106">返回一个 [Member](member-object-ado-md.md) 对象，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="882a0-106">Returns a [Member](member-object-ado-md.md) object and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="882a0-107">说明</span><span class="sxs-lookup"><span data-stu-id="882a0-107">Remarks</span></span>

<span data-ttu-id="882a0-p101">位于层次结构顶级（根）的成员没有父级。此属性仅在 **Level** 对象所属的 [Member](level-object-ado-md.md) 对象上受支持。通过属于 **Position** 对象的 [Member](position-object-ado-md.md) 对象引用此属性时，会发生错误。</span><span class="sxs-lookup"><span data-stu-id="882a0-p101">A member that is at the top level of a hierarchy (the root) has no parent. This property is supported only on **Member** objects belonging to a [Level](level-object-ado-md.md) object. An error occurs when this property is referenced from **Member** objects belonging to a [Position](position-object-ado-md.md) object.</span></span>

