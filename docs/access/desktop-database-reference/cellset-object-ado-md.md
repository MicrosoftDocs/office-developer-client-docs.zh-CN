---
title: Cellset 对象 (ADO MD)
TOCTitle: Cellset object (ADO MD)
ms:assetid: 28d4b3b9-f907-9ec0-00e1-9666c887cdf0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249047(v=office.15)
ms:contentKeyID: 48543869
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c8cb75ad7277386cfe81b2edcffa234498318444
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28702185"
---
# <a name="cellset-object-ado-md"></a><span data-ttu-id="cc347-102">Cellset 对象 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="cc347-102">Cellset object (ADO MD)</span></span>

<span data-ttu-id="cc347-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="cc347-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cc347-p101">代表多维查询的结果。它是从多维数据集或其他单元格集中选择的单元格的集合。</span><span class="sxs-lookup"><span data-stu-id="cc347-p101">Represents the results of a multidimensional query. It is a collection of cells selected from cubes or other cellsets.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc347-106">说明</span><span class="sxs-lookup"><span data-stu-id="cc347-106">Remarks</span></span>

<span data-ttu-id="cc347-p102">**Cellset** 中的数据是使用直接、类似数组的访问方式检索的。您可以"向下钻取"到特定成员以获取有关该成员的信息。例如，以下代码返回名为 cst 的单元格集的第一个轴上第一个位置中第一个成员的标题：</span><span class="sxs-lookup"><span data-stu-id="cc347-p102">Data within a **Cellset** is retrieved using direct, array-like access. You can "drill down" to a specific member to obtain data about that member. For example, the following code returns the caption of the first member in the first position on the first axis of a cellset named cst:</span></span>

`cst.Axes(0).Positions(0).Members(0).Caption`

<span data-ttu-id="cc347-p103">单元格集中没有当前单元格的观念。[Item](item-property-ado-md-cellset.md) 属性而是从单元格集中检索特定 [Cell](cell-object-ado-md.md) 对象。 **Item** 属性的参数确定要检索的单元格。您可以指定单元格的唯一序号值。还可以使用单元格沿单元格集的每条轴的位置号来检索单元格。有关检索单元格的详细信息，请参阅 [Item](item-property-ado-md-cellset.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="cc347-p103">There is no notion of a current cell within a cellset. Instead, the [Item](item-property-ado-md-cellset.md) property retrieves a specific [Cell](cell-object-ado-md.md) object from the cellset. The arguments of the **Item** property determine which cell is retrieved. You can specify the unique ordinal value of a cell. You can also retrieve cells by using their position numbers along each axis of the cellset. For more information about retrieving cells, see the [Item](item-property-ado-md-cellset.md) property.</span></span>

<span data-ttu-id="cc347-116">使用 **Cellset** 对象的集合和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="cc347-116">With the collections, methods, and properties of a **Cellset** object, you can do the following:</span></span>

  - <span data-ttu-id="cc347-117">通过设置 **Cellset** 对象的 [ActiveConnection](activeconnection-property-ado-md.md) 属性，将打开的连接与该对象关联在一起。</span><span class="sxs-lookup"><span data-stu-id="cc347-117">Associate an open connection with a **Cellset** object by setting its [ActiveConnection](activeconnection-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="cc347-118">使用 [Open](open-method-ado-md.md) 方法执行和检索多维查询的结果。</span><span class="sxs-lookup"><span data-stu-id="cc347-118">Execute and retrieve the results of a multidimensional query with the [Open](open-method-ado-md.md) method.</span></span>

  - <span data-ttu-id="cc347-119">使用 **Item** 属性从 **Cellset** 中检索 [Cell](item-property-ado-md-cellset.md) 。</span><span class="sxs-lookup"><span data-stu-id="cc347-119">Retrieve a **Cell** from the **Cellset** with the [Item](item-property-ado-md-cellset.md) property.</span></span>

  - <span data-ttu-id="cc347-120">使用 [Axes](axis-object-ado-md.md) 集合返回用于定义 **Cellset** 的 [Axis](axes-collection-ado-md.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="cc347-120">Return the [Axis](axis-object-ado-md.md) objects that define the **Cellset** with the [Axes](axes-collection-ado-md.md) collection.</span></span>

  - <span data-ttu-id="cc347-121">使用 **FilterAxis** 属性检索有关用于筛选 [Cellset](filteraxis-property-ado-md.md) 中的数据的维的信息。</span><span class="sxs-lookup"><span data-stu-id="cc347-121">Retrieve information about the dimensions used to filter the data in the **Cellset** with the [FilterAxis](filteraxis-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="cc347-122">使用 **Source** 属性返回或指定用于定义 [Cellset](source-property-ado-md.md) 的查询。</span><span class="sxs-lookup"><span data-stu-id="cc347-122">Return or specify the query used to define the **Cellset** with the [Source](source-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="cc347-123">使用 **State** 属性返回 [Cellset](state-property-ado-md.md) 的当前状态（打开、关闭、正在执行或正在连接）。</span><span class="sxs-lookup"><span data-stu-id="cc347-123">Return the current state of the **Cellset** (open, closed, executing, or connecting) with the [State](state-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="cc347-124">使用 **Close** 方法关闭打开的 [Cellset](close-method-ado-md.md) 。</span><span class="sxs-lookup"><span data-stu-id="cc347-124">Close an open **Cellset** with the [Close](close-method-ado-md.md) method.</span></span>

  - <span data-ttu-id="cc347-125">使用标准 ADO **Properties** 集合检索有关 [Cellset](properties-collection-ado.md) 的提供程序特定信息。</span><span class="sxs-lookup"><span data-stu-id="cc347-125">Retrieve provider-specific information about the **Cellset** with the standard ADO [Properties](properties-collection-ado.md) collection.</span></span>

