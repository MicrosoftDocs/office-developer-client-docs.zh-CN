---
title: FilterAxis 属性 (ADO MD)
TOCTitle: FilterAxis Property (ADO MD)
ms:assetid: 36720d77-4b16-1d17-6d80-d35265f4a8ad
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249124(v=office.15)
ms:contentKeyID: 48544172
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 912dfec595f718c2144e69b4fbd3af592f8b6d5b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466741"
---
# <a name="filteraxis-property-ado-md"></a><span data-ttu-id="614dd-102">FilterAxis 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="614dd-102">FilterAxis Property (ADO MD)</span></span>


<span data-ttu-id="614dd-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="614dd-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="614dd-104">指示有关当前单元格集的筛选信息。</span><span class="sxs-lookup"><span data-stu-id="614dd-104">Indicates filter information about the current cellset.</span></span>

## <a name="return-values"></a><span data-ttu-id="614dd-105">返回值</span><span class="sxs-lookup"><span data-stu-id="614dd-105">Return Values</span></span>

<span data-ttu-id="614dd-106">返回一个 [Axis](axis-object-ado-md.md) 对象，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="614dd-106">Returns an [Axis](axis-object-ado-md.md) object, and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="614dd-107">说明</span><span class="sxs-lookup"><span data-stu-id="614dd-107">Remarks</span></span>

<span data-ttu-id="614dd-p101">使用 **FilterAxis** 属性可返回与将数据切片时所用的维度有关的信息。 [Axis](dimensioncount-property-ado-md.md) 的 **DimensionCount** 属性返回切片器的维数。此轴通常只有一行。</span><span class="sxs-lookup"><span data-stu-id="614dd-p101">Use the **FilterAxis** property to return information about the dimensions that were used to slice the data. The [DimensionCount](dimensioncount-property-ado-md.md) property of the **Axis** returns the number of slicer dimensions. This axis usually has just one row.</span></span>

<span data-ttu-id="614dd-111">**FilterAxis** 返回的 [Axis](filteraxis-property-ado-md.md) 不包含在 [Cellset](axes-collection-ado-md.md) 对象的 [Axes](cellset-object-ado-md.md) 集合中。</span><span class="sxs-lookup"><span data-stu-id="614dd-111">The **Axis** returned by [FilterAxis](filteraxis-property-ado-md.md) is not contained in the [Axes](axes-collection-ado-md.md) collection for a [Cellset](cellset-object-ado-md.md) object.</span></span>

