---
title: FilterAxis 属性 (ADO MD)
TOCTitle: FilterAxis property (ADO MD)
ms:assetid: 36720d77-4b16-1d17-6d80-d35265f4a8ad
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249124(v=office.15)
ms:contentKeyID: 48544172
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 214de72e71a51c6b6b65bc2636a28e5650035c0a
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25926904"
---
# <a name="filteraxis-property-ado-md"></a><span data-ttu-id="7b21c-102">FilterAxis 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="7b21c-102">FilterAxis property (ADO MD)</span></span>


<span data-ttu-id="7b21c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7b21c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7b21c-104">指示有关当前单元格集的筛选信息。</span><span class="sxs-lookup"><span data-stu-id="7b21c-104">Indicates filter information about the current cellset.</span></span>

## <a name="return-values"></a><span data-ttu-id="7b21c-105">返回值</span><span class="sxs-lookup"><span data-stu-id="7b21c-105">Return values</span></span>

<span data-ttu-id="7b21c-106">返回一个 [Axis](axis-object-ado-md.md) 对象，并且该值为只读。</span><span class="sxs-lookup"><span data-stu-id="7b21c-106">Returns an [Axis](axis-object-ado-md.md) object, and is read-only.</span></span>

## <a name="remarks"></a><span data-ttu-id="7b21c-107">说明</span><span class="sxs-lookup"><span data-stu-id="7b21c-107">Remarks</span></span>

<span data-ttu-id="7b21c-p101">使用 **FilterAxis** 属性可返回与将数据切片时所用的维度有关的信息。 [Axis](dimensioncount-property-ado-md.md) 的 **DimensionCount** 属性返回切片器的维数。此轴通常只有一行。</span><span class="sxs-lookup"><span data-stu-id="7b21c-p101">Use the **FilterAxis** property to return information about the dimensions that were used to slice the data. The [DimensionCount](dimensioncount-property-ado-md.md) property of the **Axis** returns the number of slicer dimensions. This axis usually has just one row.</span></span>

<span data-ttu-id="7b21c-111">**FilterAxis** 返回的 [Axis](filteraxis-property-ado-md.md) 不包含在 [Cellset](axes-collection-ado-md.md) 对象的 [Axes](cellset-object-ado-md.md) 集合中。</span><span class="sxs-lookup"><span data-stu-id="7b21c-111">The **Axis** returned by [FilterAxis](filteraxis-property-ado-md.md) is not contained in the [Axes](axes-collection-ado-md.md) collection for a [Cellset](cellset-object-ado-md.md) object.</span></span>

