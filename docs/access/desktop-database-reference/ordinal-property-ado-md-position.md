---
title: Ordinal 属性 (ADO MD Position)
TOCTitle: Ordinal Property (ADO MD Position)
ms:assetid: fb132ab5-d2b5-317d-e885-5e37ddaf90fb
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250284(v=office.15)
ms:contentKeyID: 48548861
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: efe0fcd48d3575651096b30853c3680b0284cf52
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876797"
---
# <a name="ordinal-property-ado-md-position"></a><span data-ttu-id="479f1-102">Ordinal 属性 (ADO MD Position)</span><span class="sxs-lookup"><span data-stu-id="479f1-102">Ordinal Property (ADO MD Position)</span></span>


<span data-ttu-id="479f1-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="479f1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="479f1-104">唯一标识轴上的某个位置。</span><span class="sxs-lookup"><span data-stu-id="479f1-104">Uniquely identifies a position along an axis.</span></span>

## <a name="return-values"></a><span data-ttu-id="479f1-105">返回值</span><span class="sxs-lookup"><span data-stu-id="479f1-105">Return values</span></span>

<span data-ttu-id="479f1-106">返回一个 **Long** 整数值，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="479f1-106">Returns a **Long** integer and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="479f1-107">备注</span><span class="sxs-lookup"><span data-stu-id="479f1-107">Remarks</span></span>

<span data-ttu-id="479f1-108">**Position** 对象的 [Ordinal](position-object-ado-md.md) 对应于 **Positions** 集合中该 [Position](positions-collection-ado-md.md) 的索引。</span><span class="sxs-lookup"><span data-stu-id="479f1-108">The **Ordinal** of a [Position](position-object-ado-md.md) object corresponds to the index of the **Position** within the [Positions](positions-collection-ado-md.md) collection.</span></span>

<span data-ttu-id="479f1-109">将 **Position** 在每根轴上的 **Ordinal** 与 [Cellset](item-property-ado-md-cellset.md) 对象的 [Item](cellset-object-ado-md.md) 属性结合使用，可快速检索单元格。</span><span class="sxs-lookup"><span data-stu-id="479f1-109">A cell can quickly be retrieved using the **Ordinal** of the **Position** along each axis with the [Item](item-property-ado-md-cellset.md) property of the [Cellset](cellset-object-ado-md.md) object.</span></span>

