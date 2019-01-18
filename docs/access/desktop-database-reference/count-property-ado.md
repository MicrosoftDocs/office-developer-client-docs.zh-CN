---
title: Count 属性 (ADO)
TOCTitle: Count property (ADO)
ms:assetid: b59f9581-ffd1-471d-44fa-3c1bb812e140
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249871(v=office.15)
ms:contentKeyID: 48547253
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e2a341a82e5cdc9ed5a55ca9f4b80ba80c6875bf
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28713532"
---
# <a name="count-property-ado"></a><span data-ttu-id="154f3-102">Count 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="154f3-102">Count property (ADO)</span></span>


<span data-ttu-id="154f3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="154f3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="154f3-104">指示集合中的对象数。</span><span class="sxs-lookup"><span data-stu-id="154f3-104">Indicates the number of objects in a collection.</span></span>

## <a name="return-value"></a><span data-ttu-id="154f3-105">返回值</span><span class="sxs-lookup"><span data-stu-id="154f3-105">Return value</span></span>

<span data-ttu-id="154f3-106">返回 **Long** 值。</span><span class="sxs-lookup"><span data-stu-id="154f3-106">Returns a **Long** value.</span></span>

## <a name="remarks"></a><span data-ttu-id="154f3-107">备注</span><span class="sxs-lookup"><span data-stu-id="154f3-107">Remarks</span></span>

<span data-ttu-id="154f3-108">使用 **Count** 属性可确定在给定集合中有多少个对象。</span><span class="sxs-lookup"><span data-stu-id="154f3-108">Use the **Count** property to determine how many objects are in a given collection.</span></span>

<span data-ttu-id="154f3-p101">由于集合中的成员是从零开始进行编号的，因此应始终将循环编写为从第零个成员开始，而在 **Count** 属性的值减 1 处终止。如果在使用 Microsoft Visual Basic，而希望在不检查 **Count** 属性的情况下遍历集合的成员，则请使用 **For** **Each...Next** 命令。</span><span class="sxs-lookup"><span data-stu-id="154f3-p101">Because numbering for members of a collection begins with zero, you should always code loops starting with the zero member and ending with the value of the **Count** property minus 1. If you are using Microsoft Visual Basic and want to loop through the members of a collection without checking the **Count** property, use the **For** **Each...Next** command.</span></span>

<span data-ttu-id="154f3-111">如果 **Count** 属性为零，则表明集合中没有对象。</span><span class="sxs-lookup"><span data-stu-id="154f3-111">If the **Count** property is zero, there are no objects in the collection.</span></span>

