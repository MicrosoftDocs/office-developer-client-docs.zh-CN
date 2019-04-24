---
title: Axis 对象 (ADO MD)
TOCTitle: Axis object (ADO MD)
ms:assetid: a4332b69-8900-08f1-a4e2-9395d005ed42
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249763(v=office.15)
ms:contentKeyID: 48546807
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 23fdb0d9ba636ae58fa19b42d5a8a47cb01d4ab2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296897"
---
# <a name="axis-object-ado-md"></a><span data-ttu-id="72136-102">Axis 对象 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="72136-102">Axis object (ADO MD)</span></span>


<span data-ttu-id="72136-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="72136-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="72136-104">代表单元格集的位置轴或筛选轴，包含一维或多维的选定成员。</span><span class="sxs-lookup"><span data-stu-id="72136-104">Represents a positional or filter axis of a cellset, containing selected members of one or more dimensions.</span></span>

## <a name="remarks"></a><span data-ttu-id="72136-105">注解</span><span class="sxs-lookup"><span data-stu-id="72136-105">Remarks</span></span>

<span data-ttu-id="72136-106">**Axis** 对象可以由 [Axes](axes-collection-ado-md.md) 集合包含，或者由 [Cellset](cellset-object-ado-md.md) 的 [FilterAxis](filteraxis-property-ado-md.md) 属性返回。</span><span class="sxs-lookup"><span data-stu-id="72136-106">An **Axis** object can be contained by an [Axes](axes-collection-ado-md.md) collection, or returned by the [FilterAxis](filteraxis-property-ado-md.md) property of a [Cellset](cellset-object-ado-md.md).</span></span>

<span data-ttu-id="72136-107">使用 **Axis** 对象的集合和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="72136-107">With the collections and properties of an **Axis** object, you can do the following:</span></span>

- <span data-ttu-id="72136-108">使用 **Name** 属性标识 [Axis](name-property-ado-md.md) 。</span><span class="sxs-lookup"><span data-stu-id="72136-108">Identify the **Axis** with the [Name](name-property-ado-md.md) property.</span></span>

- <span data-ttu-id="72136-109">使用 **Positions** 集合遍历沿 [Axis](positions-collection-ado-md.md) 的每个位置。</span><span class="sxs-lookup"><span data-stu-id="72136-109">Iterate through each position along an **Axis** using the [Positions](positions-collection-ado-md.md) collection.</span></span>

- <span data-ttu-id="72136-110">使用 **DimensionCount** 属性获取 [Axis](dimensioncount-property-ado-md.md) 的维数。</span><span class="sxs-lookup"><span data-stu-id="72136-110">Obtain the number of dimensions on the **Axis** with the [DimensionCount](dimensioncount-property-ado-md.md) property.</span></span>

- <span data-ttu-id="72136-111">使用标准 ADO **Properties** 集合获取 [Axis](properties-collection-ado.md) 的提供程序特定属性。</span><span class="sxs-lookup"><span data-stu-id="72136-111">Obtain provider-specific attributes of the **Axis** with the standard ADO [Properties](properties-collection-ado.md) collection.</span></span>

