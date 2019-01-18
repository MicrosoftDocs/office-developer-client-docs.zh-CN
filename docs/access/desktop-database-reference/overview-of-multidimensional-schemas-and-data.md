---
title: 多维架构和数据概述
TOCTitle: Overview of multidimensional schemas and data
ms:assetid: a963e993-b7bf-eeb4-ecd5-d6fe43cf4bb5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249784(v=office.15)
ms:contentKeyID: 48546923
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d65378bf964ad8c6e81a08cb653f09bf00a8431c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28720217"
---
# <a name="overview-of-multidimensional-schemas-and-data"></a><span data-ttu-id="ab0a8-102">多维架构和数据概述</span><span class="sxs-lookup"><span data-stu-id="ab0a8-102">Overview of multidimensional schemas and data</span></span>

<span data-ttu-id="ab0a8-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ab0a8-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="understanding-multidimensional-schemas"></a><span data-ttu-id="ab0a8-104">了解多维架构</span><span class="sxs-lookup"><span data-stu-id="ab0a8-104">Understanding Multidimensional Schemas</span></span>

<span data-ttu-id="ab0a8-105">ADO MD 中的中心元数据对象是*多维数据集*，由相关维、层次结构、级别和成员的结构化集合构成。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-105">The central metadata object in ADO MD is the *cube*, which consists of a structured set of related dimensions, hierarchies, levels, and members.</span></span>

<span data-ttu-id="ab0a8-106">*维度*是独立的来自多维数据库，从您的业务实体派生的数据类别。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-106">A *dimension* is an independent category of data from your multidimensional database, derived from your business entities.</span></span> <span data-ttu-id="ab0a8-107">维通常包含用作数据库度量的查询条件的项目。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-107">A dimension typically contains items to be used as query criteria for the measures of the database.</span></span>

<span data-ttu-id="ab0a8-108">*层次结构*是聚合一个维度的路径。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-108">A *hierarchy* is a path of aggregation of a dimension.</span></span> <span data-ttu-id="ab0a8-109">一个维度可以有多种级别的粒度，这些粒度级别具有父子关系。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-109">A dimension may have multiple levels of granularity, which have parent-child relationships.</span></span> <span data-ttu-id="ab0a8-110">层次结构定义这些级别之间的关系。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-110">A hierarchy defines how these levels are related.</span></span>

<span data-ttu-id="ab0a8-111">*级别*为聚合层次结构中的步骤。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-111">A *level* is a step of aggregation in a hierarchy.</span></span> <span data-ttu-id="ab0a8-112">对于具有多种信息层的维，每层就是一个级别。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-112">For dimensions with multiple layers of information, each layer is a level.</span></span>

<span data-ttu-id="ab0a8-113">*成员*是维度中数据的项目。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-113">A *member* is a data item in a dimension.</span></span> <span data-ttu-id="ab0a8-114">通常，使用成员来创建标题或描述数据库度量。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-114">Typically, you create a caption or describe a measure of the database using members.</span></span>

<span data-ttu-id="ab0a8-p105">多维数据集由 ADO MD 中的 [CubeDef](cubedef-object-ado-md.md) 对象表示。维、层次结构、级别和成员也由各自相应的 ADO MD 对象表示： [Dimension](dimension-object-ado-md.md)、[Hierarchy](hierarchy-object-ado-md.md)、[Level](level-object-ado-md.md) 和 [Member](member-object-ado-md.md)。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-p105">Cubes are represented by [CubeDef](cubedef-object-ado-md.md) objects in ADO MD. Dimensions, hierarchies, levels, and members are also represented by their corresponding ADO MD objects: [Dimension](dimension-object-ado-md.md), [Hierarchy](hierarchy-object-ado-md.md), [Level](level-object-ado-md.md), and [Member](member-object-ado-md.md).</span></span>

## <a name="dimensions"></a><span data-ttu-id="ab0a8-117">维度</span><span class="sxs-lookup"><span data-stu-id="ab0a8-117">Dimensions</span></span>

<span data-ttu-id="ab0a8-p106">多维数据集的维取决于您的业务实体和要在数据库中建模的数据类型。通常，每个维是一个用于选择数据的独立入口点或机制。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-p106">The dimensions of a cube depend on your business entities and types of data to be modeled in the database. Typically, each dimension is an independent entry point or mechanism for selecting data.</span></span>

<span data-ttu-id="ab0a8-p107">例如，包含销售数据的多维数据集具有以下五个维：Salesperson、Geography、Time、Products 和 Measures。Measures 维包含实际的销售数据值，而其他维则表示对销售数据值进行分类和分组的方式。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-p107">For example, a cube containing sales data has the following five dimensions: Salesperson, Geography, Time, Products, and Measures. The Measures dimension contains actual sales data values, while the other dimensions represent ways to categorize and group the sales data values.</span></span>

<span data-ttu-id="ab0a8-122">Geography 维具有以下成员集：</span><span class="sxs-lookup"><span data-stu-id="ab0a8-122">The Geography dimension has the following set of members:</span></span>

```text
 
{All, North America, Europe, Canada, USA, UK, Germany, Canada-West, 
Canada-East, USA-NW, USA-SW, USA-NE, USA-SE, England, Scotland,  
Wales,Ireland, Germany-North, Germany-South, Ottawa, Toronto,  
Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston,  
Shreveport, Miami, Boston, New York, London, Dover, Glasgow,  
Edinburgh, Cardiff, Pembroke, Belfast, Berlin,  
Hamburg, Munich, Stuttgart} 
```

## <a name="hierarchies"></a><span data-ttu-id="ab0a8-123">层次结构</span><span class="sxs-lookup"><span data-stu-id="ab0a8-123">Hierarchies</span></span>

<span data-ttu-id="ab0a8-p108">层次结构定义可以对维的级别进行"汇总"或分组的方式。一个维可以有多个层次结构。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-p108">Hierarchies define the ways in which the levels of a dimension can be "rolled up" or grouped. A dimension can have more than one hierarchy.</span></span>

## <a name="levels"></a><span data-ttu-id="ab0a8-126">级别</span><span class="sxs-lookup"><span data-stu-id="ab0a8-126">Levels</span></span>

<span data-ttu-id="ab0a8-127">在上图说明的 Geography 维示例中，每个框代表层次结构中的一个级别。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-127">In the example Geography dimension pictured in the previous figure, each box represents a level in the hierarchy.</span></span>

<span data-ttu-id="ab0a8-128">每个级别都有一组成员，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ab0a8-128">Each level has a set of members, as follows:</span></span>

  - <span data-ttu-id="ab0a8-129">The World = {All}
</span><span class="sxs-lookup"><span data-stu-id="ab0a8-129">The World = {All}</span></span>

  - <span data-ttu-id="ab0a8-130">Continents = {North America, Europe}
</span><span class="sxs-lookup"><span data-stu-id="ab0a8-130">Continents = {North America, Europe}</span></span>

  - <span data-ttu-id="ab0a8-131">Countries = {Canada, USA, UK, Germany}
</span><span class="sxs-lookup"><span data-stu-id="ab0a8-131">Countries = {Canada, USA, UK, Germany}</span></span>

  - <span data-ttu-id="ab0a8-132">Regions = {Canada-East, Canada-West, USA-NE, USA-NW, USA-SE, USA-SW, England, Ireland, Scotland, Wales, Germany-North, Germany-South}
</span><span class="sxs-lookup"><span data-stu-id="ab0a8-132">Regions = {Canada-East, Canada-West, USA-NE, USA-NW, USA-SE, USA-SW, England, Ireland, Scotland, Wales, Germany-North, Germany-South}</span></span>

  - <span data-ttu-id="ab0a8-133">Cities = {Ottawa, Toronto, Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston, Shreveport, Miami, Boston, New York, London, Dover, Glasgow, Edinburgh, Cardiff, Pembroke, Belfast, Berlin, Hamburg, Munich, Stuttgart}
</span><span class="sxs-lookup"><span data-stu-id="ab0a8-133">Cities = {Ottawa, Toronto, Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston, Shreveport, Miami, Boston, New York, London, Dover, Glasgow, Edinburgh, Cardiff, Pembroke, Belfast, Berlin, Hamburg, Munich, Stuttgart}</span></span>

## <a name="members"></a><span data-ttu-id="ab0a8-134">成员</span><span class="sxs-lookup"><span data-stu-id="ab0a8-134">Members</span></span>

<span data-ttu-id="ab0a8-p109">位于层次结构叶级别的成员没有子级，且位于根级别的成员没有父级。所有其他成员具有至少一个父级和至少一个子级。例如，Geography 维中的层次结构树的部分遍历会产生以下父子关系：</span><span class="sxs-lookup"><span data-stu-id="ab0a8-p109">Members at the leaf level of a hierarchy have no children, and members at the root level have no parent. All other members have at least one parent and at least one child. For example, a partial traversal of the hierarchy tree in the Geography dimension yields the following parent-child relationships:</span></span>

- <span data-ttu-id="ab0a8-138">{所有}（的父对象）{欧洲、 北美洲}</span><span class="sxs-lookup"><span data-stu-id="ab0a8-138">{All} (parent of) {Europe, North America}</span></span>
- <span data-ttu-id="ab0a8-139">{北美}（的父对象）{加拿大，美国}</span><span class="sxs-lookup"><span data-stu-id="ab0a8-139">{North America} (parent of) {Canada, USA}</span></span>
- <span data-ttu-id="ab0a8-140">{USA}（的父对象）{USA NE，美国-NW，美国 SE，美国-软件}</span><span class="sxs-lookup"><span data-stu-id="ab0a8-140">{USA} (parent of) {USA-NE, USA-NW, USA-SE, USA-SW}</span></span>
- <span data-ttu-id="ab0a8-141">{USA NW}（的父对象）{博伊西，西雅图}</span><span class="sxs-lookup"><span data-stu-id="ab0a8-141">{USA-NW} (parent of) {Boise, Seattle}</span></span>

<span data-ttu-id="ab0a8-142">可以合并每个维的一个或多个层次结构的成员。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-142">Members can be consolidated along one or more hierarchies per dimension.</span></span>

<span data-ttu-id="ab0a8-143">此示例还演示了其他特征： 年周层次结构的周级别的某些成员不出现在任何年季度层次结构的级别。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-143">This example also illustrates another characteristic: some members of the Week level of the Year-Week hierarchy do not appear in any level of the Year-Quarter hierarchy.</span></span> <span data-ttu-id="ab0a8-144">这样，层次结构就不需要包括维的所有成员。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-144">Thus, a hierarchy need not include all members of a dimension.</span></span>

## <a name="understanding-multidimensional-schemas"></a><span data-ttu-id="ab0a8-145">了解多维架构</span><span class="sxs-lookup"><span data-stu-id="ab0a8-145">Understanding Multidimensional Schemas</span></span>

<span data-ttu-id="ab0a8-146">ADO MD 中的中心元数据对象是*多维数据集*，由相关维、层次结构、级别和成员的结构化集合构成。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-146">The central metadata object in ADO MD is the *cube*, which consists of a structured set of related dimensions, hierarchies, levels, and members.</span></span>

<span data-ttu-id="ab0a8-147">*维度*是独立的来自多维数据库，从您的业务实体派生的数据类别。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-147">A *dimension* is an independent category of data from your multidimensional database, derived from your business entities.</span></span> <span data-ttu-id="ab0a8-148">维通常包含用作数据库度量的查询条件的项目。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-148">A dimension typically contains items to be used as query criteria for the measures of the database.</span></span>

<span data-ttu-id="ab0a8-149">*层次结构*是聚合一个维度的路径。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-149">A *hierarchy* is a path of aggregation of a dimension.</span></span> <span data-ttu-id="ab0a8-150">一个维度可以有多种级别的粒度，这些粒度级别具有父子关系。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-150">A dimension may have multiple levels of granularity, which have parent-child relationships.</span></span> <span data-ttu-id="ab0a8-151">层次结构定义这些级别之间的关系。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-151">A hierarchy defines how these levels are related.</span></span>

<span data-ttu-id="ab0a8-152">*级别*为聚合层次结构中的步骤。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-152">A *level* is a step of aggregation in a hierarchy.</span></span> <span data-ttu-id="ab0a8-153">对于具有多种信息层的维，每层就是一个级别。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-153">For dimensions with multiple layers of information, each layer is a level.</span></span>

<span data-ttu-id="ab0a8-154">*成员*是维度中数据的项目。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-154">A *member* is a data item in a dimension.</span></span> <span data-ttu-id="ab0a8-155">通常，使用成员来创建标题或描述数据库度量。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-155">Typically, you create a caption or describe a measure of the database using members.</span></span>

<span data-ttu-id="ab0a8-p115">多维数据集由 ADO MD 中的 [CubeDef](cubedef-object-ado-md.md) 对象表示。维、层次结构、级别和成员也由各自相应的 ADO MD 对象表示： [Dimension](dimension-object-ado-md.md)、[Hierarchy](hierarchy-object-ado-md.md)、[Level](level-object-ado-md.md) 和 [Member](member-object-ado-md.md)。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-p115">Cubes are represented by [CubeDef](cubedef-object-ado-md.md) objects in ADO MD. Dimensions, hierarchies, levels, and members are also represented by their corresponding ADO MD objects: [Dimension](dimension-object-ado-md.md), [Hierarchy](hierarchy-object-ado-md.md), [Level](level-object-ado-md.md), and [Member](member-object-ado-md.md).</span></span>

## <a name="dimensions"></a><span data-ttu-id="ab0a8-158">维度</span><span class="sxs-lookup"><span data-stu-id="ab0a8-158">Dimensions</span></span>

<span data-ttu-id="ab0a8-p116">多维数据集的维取决于您的业务实体和要在数据库中建模的数据类型。通常，每个维是一个用于选择数据的独立入口点或机制。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-p116">The dimensions of a cube depend on your business entities and types of data to be modeled in the database. Typically, each dimension is an independent entry point or mechanism for selecting data.</span></span>

<span data-ttu-id="ab0a8-p117">例如，包含销售数据的多维数据集具有以下五个维：Salesperson、Geography、Time、Products 和 Measures。Measures 维包含实际的销售数据值，而其他维则表示对销售数据值进行分类和分组的方式。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-p117">For example, a cube containing sales data has the following five dimensions: Salesperson, Geography, Time, Products, and Measures. The Measures dimension contains actual sales data values, while the other dimensions represent ways to categorize and group the sales data values.</span></span>

<span data-ttu-id="ab0a8-163">Geography 维具有以下成员集：</span><span class="sxs-lookup"><span data-stu-id="ab0a8-163">The Geography dimension has the following set of members:</span></span>

```text 
 
{All, North America, Europe, Canada, USA, UK, Germany, Canada-West, 
Canada-East, USA-NW, USA-SW, USA-NE, USA-SE, England, Scotland,  
Wales,Ireland, Germany-North, Germany-South, Ottawa, Toronto,  
Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston,  
Shreveport, Miami, Boston, New York, London, Dover, Glasgow,  
Edinburgh, Cardiff, Pembroke, Belfast, Berlin,  
Hamburg, Munich, Stuttgart} 
```

## <a name="hierarchies"></a><span data-ttu-id="ab0a8-164">层次结构</span><span class="sxs-lookup"><span data-stu-id="ab0a8-164">Hierarchies</span></span>

<span data-ttu-id="ab0a8-p118">层次结构定义可以对维的级别进行"汇总"或分组的方式。一个维可以有多个层次结构。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-p118">Hierarchies define the ways in which the levels of a dimension can be "rolled up" or grouped. A dimension can have more than one hierarchy.</span></span>

## <a name="levels"></a><span data-ttu-id="ab0a8-167">级别</span><span class="sxs-lookup"><span data-stu-id="ab0a8-167">Levels</span></span>

<span data-ttu-id="ab0a8-168">在上图说明的 Geography 维示例中，每个框代表层次结构中的一个级别。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-168">In the example Geography dimension pictured in the previous figure, each box represents a level in the hierarchy.</span></span>

<span data-ttu-id="ab0a8-169">每个级别都有一组成员，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ab0a8-169">Each level has a set of members, as follows:</span></span>

- <span data-ttu-id="ab0a8-170">The World = {All}
</span><span class="sxs-lookup"><span data-stu-id="ab0a8-170">The World = {All}</span></span>

- <span data-ttu-id="ab0a8-171">Continents = {North America, Europe}
</span><span class="sxs-lookup"><span data-stu-id="ab0a8-171">Continents = {North America, Europe}</span></span>

- <span data-ttu-id="ab0a8-172">Countries = {Canada, USA, UK, Germany}
</span><span class="sxs-lookup"><span data-stu-id="ab0a8-172">Countries = {Canada, USA, UK, Germany}</span></span>

- <span data-ttu-id="ab0a8-173">Regions = {Canada-East, Canada-West, USA-NE, USA-NW, USA-SE, USA-SW, England, Ireland, Scotland, Wales, Germany-North, Germany-South}
</span><span class="sxs-lookup"><span data-stu-id="ab0a8-173">Regions = {Canada-East, Canada-West, USA-NE, USA-NW, USA-SE, USA-SW, England, Ireland, Scotland, Wales, Germany-North, Germany-South}</span></span>

- <span data-ttu-id="ab0a8-174">Cities = {Ottawa, Toronto, Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston, Shreveport, Miami, Boston, New York, London, Dover, Glasgow, Edinburgh, Cardiff, Pembroke, Belfast, Berlin, Hamburg, Munich, Stuttgart}
</span><span class="sxs-lookup"><span data-stu-id="ab0a8-174">Cities = {Ottawa, Toronto, Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston, Shreveport, Miami, Boston, New York, London, Dover, Glasgow, Edinburgh, Cardiff, Pembroke, Belfast, Berlin, Hamburg, Munich, Stuttgart}</span></span>

## <a name="members"></a><span data-ttu-id="ab0a8-175">成员</span><span class="sxs-lookup"><span data-stu-id="ab0a8-175">Members</span></span>

<span data-ttu-id="ab0a8-p119">位于层次结构叶级别的成员没有子级，且位于根级别的成员没有父级。所有其他成员具有至少一个父级和至少一个子级。例如，Geography 维中的层次结构树的部分遍历会产生以下父子关系：</span><span class="sxs-lookup"><span data-stu-id="ab0a8-p119">Members at the leaf level of a hierarchy have no children, and members at the root level have no parent. All other members have at least one parent and at least one child. For example, a partial traversal of the hierarchy tree in the Geography dimension yields the following parent-child relationships:</span></span>

- <span data-ttu-id="ab0a8-179">{所有}（的父对象）{欧洲、 北美洲}</span><span class="sxs-lookup"><span data-stu-id="ab0a8-179">{All} (parent of) {Europe, North America}</span></span>

- <span data-ttu-id="ab0a8-180">{北美}（的父对象）{加拿大，美国}</span><span class="sxs-lookup"><span data-stu-id="ab0a8-180">{North America} (parent of) {Canada, USA}</span></span>

- <span data-ttu-id="ab0a8-181">{USA}（的父对象）{USA NE，美国-NW，美国 SE，美国-软件}</span><span class="sxs-lookup"><span data-stu-id="ab0a8-181">{USA} (parent of) {USA-NE, USA-NW, USA-SE, USA-SW}</span></span>

- <span data-ttu-id="ab0a8-182">{USA NW}（的父对象）{博伊西，西雅图}</span><span class="sxs-lookup"><span data-stu-id="ab0a8-182">{USA-NW} (parent of) {Boise, Seattle}</span></span>

<span data-ttu-id="ab0a8-183">可以合并每个维的一个或多个层次结构的成员。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-183">Members can be consolidated along one or more hierarchies per dimension.</span></span>

<span data-ttu-id="ab0a8-184">此示例还演示了其他特征： 年周层次结构的周级别的某些成员不出现在任何年季度层次结构的级别。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-184">This example also illustrates another characteristic: some members of the Week level of the Year-Week hierarchy do not appear in any level of the Year-Quarter hierarchy.</span></span> <span data-ttu-id="ab0a8-185">这样，层次结构就不需要包括维的所有成员。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-185">Thus, a hierarchy need not include all members of a dimension.</span></span>

