---
title: DrilledDown 属性 (ADO MD)
TOCTitle: DrilledDown Property (ADO MD)
ms:assetid: 1dfe728f-8da2-1d2b-7361-8689a0b088b4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248972(v=office.15)
ms:contentKeyID: 48543610
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f8d203513ce88998143d3043e76ce6ffb6a64741
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465556"
---
# <a name="drilleddown-property-ado-md"></a><span data-ttu-id="615bf-102">DrilledDown 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="615bf-102">DrilledDown Property (ADO MD)</span></span>


<span data-ttu-id="615bf-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="615bf-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="615bf-104">指示该成员在轴上是否有直接子级。</span><span class="sxs-lookup"><span data-stu-id="615bf-104">Indicates whether no children immediately follow the member on the axis.</span></span>

## <a name="return-values"></a><span data-ttu-id="615bf-105">返回值</span><span class="sxs-lookup"><span data-stu-id="615bf-105">Return Values</span></span>

<span data-ttu-id="615bf-p101">返回一个 **Boolean** 值，并且是只读的。如果当前成员在轴上没有子成员，则 **DrilledDown** 返回 **True** 。如果当前成员在轴上有一个或多个子级成员，则 **DrilledDown** 返回 **False** 。</span><span class="sxs-lookup"><span data-stu-id="615bf-p101">Returns a **Boolean** value and is read-only. **DrilledDown** returns **True** if there are no child members of the current member on the axis. **DrilledDown** returns **False** if there is one or more child members of the current member on the axis.</span></span>

## <a name="remarks"></a><span data-ttu-id="615bf-109">说明</span><span class="sxs-lookup"><span data-stu-id="615bf-109">Remarks</span></span>

<span data-ttu-id="615bf-p102">使用 **DrilledDown** 属性可确定此成员在轴上是否至少有一个直接子成员。此信息在显示成员时很有用。</span><span class="sxs-lookup"><span data-stu-id="615bf-p102">Use the **DrilledDown** property to determine whether there is at least one child of this member on the axis immediately following this member. This information is useful when displaying the member.</span></span>

<span data-ttu-id="615bf-p103">此属性仅在 [Position](member-object-ado-md.md) 对象所属的 [Member](position-object-ado-md.md) 对象上受支持。从 **Level** 对象所属的 [Member](level-object-ado-md.md) 对象引用此属性时，会发生错误。</span><span class="sxs-lookup"><span data-stu-id="615bf-p103">This property is only supported on [Member](member-object-ado-md.md) objects belonging to a [Position](position-object-ado-md.md) object. An error occurs when this property is referenced from **Member** objects belonging to a [Level](level-object-ado-md.md) object.</span></span>
