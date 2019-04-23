---
title: Members 集合 (ADO MD)
TOCTitle: Members collection (ADO MD)
ms:assetid: 1389c554-e4f1-107d-22c6-7fe851d53d23
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248910(v=office.15)
ms:contentKeyID: 48543371
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: adc8ed771bcba6a4b6532b33b27980f8aab695c5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289239"
---
# <a name="members-collection-ado-md"></a><span data-ttu-id="c4dd0-102">Members 集合 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="c4dd0-102">Members collection (ADO MD)</span></span>


<span data-ttu-id="c4dd0-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c4dd0-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c4dd0-104">包含来自某个级别或轴上某个位置的 [Member](member-object-ado-md.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="c4dd0-104">Contains the [Member](member-object-ado-md.md) objects from a level or a position along an axis.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4dd0-105">注解</span><span class="sxs-lookup"><span data-stu-id="c4dd0-105">Remarks</span></span>

<span data-ttu-id="c4dd0-106">**Members** 集合用于包含下列类型的成员：</span><span class="sxs-lookup"><span data-stu-id="c4dd0-106">A **Members** collection is used to contain the following types of members:</span></span>

  - <span data-ttu-id="c4dd0-p101">构成多维数据集中的某一级别的成员。它们包含在 **Level** 对象的 [Members](level-object-ado-md.md) 集合中。例如，使用 [多维架构和数据概述](overview-of-multidimensional-schemas-and-data.md)中的示例时，Countries 级别的四个成员为 Canada、USA、UK 和 Germany。</span><span class="sxs-lookup"><span data-stu-id="c4dd0-p101">The members that make up a level in a cube. These are contained in the **Members** collection of a [Level](level-object-ado-md.md) object. For example, using the sample from [Overview of Multidimensional Schemas and Data](overview-of-multidimensional-schemas-and-data.md), the four members of the Countries level are Canada, USA, UK, and Germany.</span></span>

  - <span data-ttu-id="c4dd0-p102">属于层次结构中特定成员的子级的成员。这些成员由父 [Member](children-property-ado-md.md) 对象的 **Children** 属性返回。例如，还是使用同一示例，Canada 成员的两个子级为 Canada-East 和 Canada-West。</span><span class="sxs-lookup"><span data-stu-id="c4dd0-p102">The members that are the children of a specific member within a hierarchy. These members are returned by the [Children](children-property-ado-md.md) property of the parent **Member** object. For example, again using the same sample, the two children of the Canada member are Canada-East and Canada-West.</span></span>

  - <span data-ttu-id="c4dd0-p103">定义沿[单元格集](cellset-object-ado-md.md)的轴的特定位置的成员。使用[处理多维数据](working-with-multidimensional-data.md)中的单元格集作为示例时，x 轴上第一个位置的两个成员为 Valentine 和 Seattle。这些成员包含在 **Position** 对象的 [Members](position-object-ado-md.md) 集合中。</span><span class="sxs-lookup"><span data-stu-id="c4dd0-p103">The members that define a specific position along an axis of a [cellset](cellset-object-ado-md.md). Using the cellset from [Working with Multidimensional Data](working-with-multidimensional-data.md) as an example, the two members of the first position on the x-axis are Valentine and Seattle. These members are contained by the **Members** collection of a [Position](position-object-ado-md.md) object.</span></span>

<span data-ttu-id="c4dd0-p104">**Members** 是一个标准 ADO 集合。使用集合的属性和方法，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c4dd0-p104">**Members** is a standard ADO collection. With the properties and methods of a collection, you can do the following:</span></span>

  - <span data-ttu-id="c4dd0-118">使用 [Count](count-property-ado.md) 属性获取集合中的对象数。</span><span class="sxs-lookup"><span data-stu-id="c4dd0-118">Obtain the number of objects in the collection with the [Count](count-property-ado.md) property.</span></span>

  - <span data-ttu-id="c4dd0-119">使用默认的 [Item](item-property-ado.md) 属性返回集合中的某个对象。</span><span class="sxs-lookup"><span data-stu-id="c4dd0-119">Return an object from the collection with the default [Item](item-property-ado.md) property.</span></span>

  - <span data-ttu-id="c4dd0-120">使用 [Refresh](refresh-method-ado.md) 方法更新来自提供程序的集合中的对象。</span><span class="sxs-lookup"><span data-stu-id="c4dd0-120">Update the objects in the collection from the provider with the [Refresh](refresh-method-ado.md) method.</span></span>

