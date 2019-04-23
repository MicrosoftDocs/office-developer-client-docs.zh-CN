---
title: Ordinal 属性（ADO MD 位置）
TOCTitle: Ordinal property (ADO MD Position)
ms:assetid: fb132ab5-d2b5-317d-e885-5e37ddaf90fb
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250284(v=office.15)
ms:contentKeyID: 48548861
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2e29b5c86e8f37d84116aa92432e93eb8943e29e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288188"
---
# <a name="ordinal-property-ado-md-position"></a><span data-ttu-id="fa279-102">Ordinal 属性（ADO MD 位置）</span><span class="sxs-lookup"><span data-stu-id="fa279-102">Ordinal property (ADO MD Position)</span></span>


<span data-ttu-id="fa279-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="fa279-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fa279-104">唯一标识轴上的某个位置。</span><span class="sxs-lookup"><span data-stu-id="fa279-104">Uniquely identifies a position along an axis.</span></span>

## <a name="return-values"></a><span data-ttu-id="fa279-105">返回值</span><span class="sxs-lookup"><span data-stu-id="fa279-105">Return values</span></span>

<span data-ttu-id="fa279-106">返回一个 **Long** 整数值，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="fa279-106">Returns a **Long** integer and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa279-107">注解</span><span class="sxs-lookup"><span data-stu-id="fa279-107">Remarks</span></span>

<span data-ttu-id="fa279-108">[Position](position-object-ado-md.md) 对象的 **Ordinal** 对应于 [Positions](positions-collection-ado-md.md) 集合中该 **Position** 的索引。</span><span class="sxs-lookup"><span data-stu-id="fa279-108">The **Ordinal** of a [Position](position-object-ado-md.md) object corresponds to the index of the **Position** within the [Positions](positions-collection-ado-md.md) collection.</span></span>

<span data-ttu-id="fa279-109">将 **Position** 在每根轴上的 **Ordinal** 与 [Cellset](item-property-ado-md-cellset.md) 对象的 [Item](cellset-object-ado-md.md) 属性结合使用，可快速检索单元格。</span><span class="sxs-lookup"><span data-stu-id="fa279-109">A cell can quickly be retrieved using the **Ordinal** of the **Position** along each axis with the [Item](item-property-ado-md-cellset.md) property of the [Cellset](cellset-object-ado-md.md) object.</span></span>

