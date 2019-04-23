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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288152"
---
# <a name="overview-of-multidimensional-schemas-and-data"></a><span data-ttu-id="77d3b-102">多维架构和数据概述</span><span class="sxs-lookup"><span data-stu-id="77d3b-102">Overview of multidimensional schemas and data</span></span>

<span data-ttu-id="77d3b-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="77d3b-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="understanding-multidimensional-schemas"></a><span data-ttu-id="77d3b-104">了解多维架构</span><span class="sxs-lookup"><span data-stu-id="77d3b-104">Understanding Multidimensional Schemas</span></span>

<span data-ttu-id="77d3b-105">ADO MD 中的中心元数据对象是*多维数据集*，由相关维、层次结构、级别和成员的结构化集合构成。</span><span class="sxs-lookup"><span data-stu-id="77d3b-105">The central metadata object in ADO MD is the *cube*, which consists of a structured set of related dimensions, hierarchies, levels, and members.</span></span>

<span data-ttu-id="77d3b-p101">*维*是来自多维数据库中的一种独立的数据类别，派生于您的业务实体。维通常包含用作数据库度量的查询条件的项目。</span><span class="sxs-lookup"><span data-stu-id="77d3b-p101">A *dimension* is an independent category of data from your multidimensional database, derived from your business entities. A dimension typically contains items to be used as query criteria for the measures of the database.</span></span>

<span data-ttu-id="77d3b-p102">*层次结构*是维度聚合的路径。一个维度可以有多种级别的粒度，这些粒度级别具有父子关系。层次结构定义这些级别之间的关系。</span><span class="sxs-lookup"><span data-stu-id="77d3b-p102">A *hierarchy* is a path of aggregation of a dimension. A dimension may have multiple levels of granularity, which have parent-child relationships. A hierarchy defines how these levels are related.</span></span>

<span data-ttu-id="77d3b-111">*级别*是层次结构中的聚合步骤。</span><span class="sxs-lookup"><span data-stu-id="77d3b-111">A *level* is a step of aggregation in a hierarchy.</span></span> <span data-ttu-id="77d3b-112">对于具有多种信息层的维，每层就是一个级别。</span><span class="sxs-lookup"><span data-stu-id="77d3b-112">For dimensions with multiple layers of information, each layer is a level.</span></span>

<span data-ttu-id="77d3b-113">*成员*是维中的数据项。</span><span class="sxs-lookup"><span data-stu-id="77d3b-113">A *member* is a data item in a dimension.</span></span> <span data-ttu-id="77d3b-114">通常，使用成员来创建标题或描述数据库度量。</span><span class="sxs-lookup"><span data-stu-id="77d3b-114">Typically, you create a caption or describe a measure of the database using members.</span></span>

<span data-ttu-id="77d3b-p105">多维数据集由 ADO MD 中的 [CubeDef](cubedef-object-ado-md.md) 对象表示。维、层次结构、级别和成员也由各自相应的 ADO MD 对象表示： [Dimension](dimension-object-ado-md.md)、[Hierarchy](hierarchy-object-ado-md.md)、[Level](level-object-ado-md.md) 和 [Member](member-object-ado-md.md)。</span><span class="sxs-lookup"><span data-stu-id="77d3b-p105">Cubes are represented by [CubeDef](cubedef-object-ado-md.md) objects in ADO MD. Dimensions, hierarchies, levels, and members are also represented by their corresponding ADO MD objects: [Dimension](dimension-object-ado-md.md), [Hierarchy](hierarchy-object-ado-md.md), [Level](level-object-ado-md.md), and [Member](member-object-ado-md.md).</span></span>

## <a name="dimensions"></a><span data-ttu-id="77d3b-117">Dimensions</span><span class="sxs-lookup"><span data-stu-id="77d3b-117">Dimensions</span></span>

<span data-ttu-id="77d3b-p106">多维数据集的维取决于您的业务实体和要在数据库中建模的数据类型。通常，每个维是一个用于选择数据的独立入口点或机制。</span><span class="sxs-lookup"><span data-stu-id="77d3b-p106">The dimensions of a cube depend on your business entities and types of data to be modeled in the database. Typically, each dimension is an independent entry point or mechanism for selecting data.</span></span>

<span data-ttu-id="77d3b-p107">例如，包含销售数据的多维数据集具有以下五个维：Salesperson、Geography、Time、Products 和 Measures。Measures 维包含实际的销售数据值，而其他维则表示对销售数据值进行分类和分组的方式。</span><span class="sxs-lookup"><span data-stu-id="77d3b-p107">For example, a cube containing sales data has the following five dimensions: Salesperson, Geography, Time, Products, and Measures. The Measures dimension contains actual sales data values, while the other dimensions represent ways to categorize and group the sales data values.</span></span>

<span data-ttu-id="77d3b-122">Geography 维具有以下成员集：</span><span class="sxs-lookup"><span data-stu-id="77d3b-122">The Geography dimension has the following set of members:</span></span>

```text
 
{All, North America, Europe, Canada, USA, UK, Germany, Canada-West, 
Canada-East, USA-NW, USA-SW, USA-NE, USA-SE, England, Scotland,  
Wales,Ireland, Germany-North, Germany-South, Ottawa, Toronto,  
Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston,  
Shreveport, Miami, Boston, New York, London, Dover, Glasgow,  
Edinburgh, Cardiff, Pembroke, Belfast, Berlin,  
Hamburg, Munich, Stuttgart} 
```

## <a name="hierarchies"></a><span data-ttu-id="77d3b-123">Hierarchies</span><span class="sxs-lookup"><span data-stu-id="77d3b-123">Hierarchies</span></span>

<span data-ttu-id="77d3b-p108">层次结构定义可以对维的级别进行“汇总”或分组的方式。一个维可以有多个层次结构。</span><span class="sxs-lookup"><span data-stu-id="77d3b-p108">Hierarchies define the ways in which the levels of a dimension can be "rolled up" or grouped. A dimension can have more than one hierarchy.</span></span>

## <a name="levels"></a><span data-ttu-id="77d3b-126">Levels</span><span class="sxs-lookup"><span data-stu-id="77d3b-126">Levels</span></span>

<span data-ttu-id="77d3b-127">在上图说明的 Geography 维示例中，每个框代表层次结构中的一个级别。</span><span class="sxs-lookup"><span data-stu-id="77d3b-127">In the example Geography dimension pictured in the previous figure, each box represents a level in the hierarchy.</span></span>

<span data-ttu-id="77d3b-128">每个级别都有一组成员，如下所示：</span><span class="sxs-lookup"><span data-stu-id="77d3b-128">Each level has a set of members, as follows:</span></span>

  - <span data-ttu-id="77d3b-129">The World = {All}
</span><span class="sxs-lookup"><span data-stu-id="77d3b-129">The World = {All}</span></span>

  - <span data-ttu-id="77d3b-130">洲 = {北美、欧洲}</span><span class="sxs-lookup"><span data-stu-id="77d3b-130">Continents = {North America, Europe}</span></span>

  - <span data-ttu-id="77d3b-131">国家/地区 = {加拿大, 美国, 英国, 德国}</span><span class="sxs-lookup"><span data-stu-id="77d3b-131">Countries = {Canada, USA, UK, Germany}</span></span>

  - <span data-ttu-id="77d3b-132">地区 = {加拿大-东部, 加拿大-西部, 美国-NE, 美国-NW, 美国-SE, 美国-SW, 英国, 爱尔兰, 苏格兰, 威尔士, 德国-北部, 德国-南部}</span><span class="sxs-lookup"><span data-stu-id="77d3b-132">Regions = {Canada-East, Canada-West, USA-NE, USA-NW, USA-SE, USA-SW, England, Ireland, Scotland, Wales, Germany-North, Germany-South}</span></span>

  - <span data-ttu-id="77d3b-133">城市 = {渥太华、多伦多、范 Boise、卡尔加里、西雅图、、洛杉矶、休斯顿、Shreveport、迈阿密、波士顿、纽约、伦敦、Dover、Glasgow、爱丁堡、Cardiff、Pembroke、Belfast、柏林、Hamburg、慕尼黑、斯图加特}</span><span class="sxs-lookup"><span data-stu-id="77d3b-133">Cities = {Ottawa, Toronto, Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston, Shreveport, Miami, Boston, New York, London, Dover, Glasgow, Edinburgh, Cardiff, Pembroke, Belfast, Berlin, Hamburg, Munich, Stuttgart}</span></span>

## <a name="members"></a><span data-ttu-id="77d3b-134">Members</span><span class="sxs-lookup"><span data-stu-id="77d3b-134">Members</span></span>

<span data-ttu-id="77d3b-p109">位于层次结构叶级别的成员没有子级，且位于根级别的成员没有父级。所有其他成员具有至少一个父级和至少一个子级。例如，Geography 维中的层次结构树的部分遍历会产生以下父子关系：</span><span class="sxs-lookup"><span data-stu-id="77d3b-p109">Members at the leaf level of a hierarchy have no children, and members at the root level have no parent. All other members have at least one parent and at least one child. For example, a partial traversal of the hierarchy tree in the Geography dimension yields the following parent-child relationships:</span></span>

- <span data-ttu-id="77d3b-138">各种(的父级){欧洲, 北美}</span><span class="sxs-lookup"><span data-stu-id="77d3b-138">{All} (parent of) {Europe, North America}</span></span>
- <span data-ttu-id="77d3b-139">{北美}(的父级){加拿大, 美国}</span><span class="sxs-lookup"><span data-stu-id="77d3b-139">{North America} (parent of) {Canada, USA}</span></span>
- <span data-ttu-id="77d3b-140">特区(的父级){美国-NE, 美国-NW, 美国-SE, 美国-SW}</span><span class="sxs-lookup"><span data-stu-id="77d3b-140">{USA} (parent of) {USA-NE, USA-NW, USA-SE, USA-SW}</span></span>
- <span data-ttu-id="77d3b-141">{美国-NW}(的父级){Boise, 西雅图}</span><span class="sxs-lookup"><span data-stu-id="77d3b-141">{USA-NW} (parent of) {Boise, Seattle}</span></span>

<span data-ttu-id="77d3b-142">可以合并每个维的一个或多个层次结构的成员。</span><span class="sxs-lookup"><span data-stu-id="77d3b-142">Members can be consolidated along one or more hierarchies per dimension.</span></span>

<span data-ttu-id="77d3b-143">本示例还演示了另一个特征: 一年的第一周层次结构中的某些成员不会出现在任何级别的年季度层次结构中。</span><span class="sxs-lookup"><span data-stu-id="77d3b-143">This example also illustrates another characteristic: some members of the Week level of the Year-Week hierarchy do not appear in any level of the Year-Quarter hierarchy.</span></span> <span data-ttu-id="77d3b-144">这样，层次结构就不需要包括维的所有成员。</span><span class="sxs-lookup"><span data-stu-id="77d3b-144">Thus, a hierarchy need not include all members of a dimension.</span></span>

## <a name="understanding-multidimensional-schemas"></a><span data-ttu-id="77d3b-145">了解多维架构</span><span class="sxs-lookup"><span data-stu-id="77d3b-145">Understanding Multidimensional Schemas</span></span>

<span data-ttu-id="77d3b-146">ADO MD 中的中心元数据对象是*多维数据集*，由相关维、层次结构、级别和成员的结构化集合构成。</span><span class="sxs-lookup"><span data-stu-id="77d3b-146">The central metadata object in ADO MD is the *cube*, which consists of a structured set of related dimensions, hierarchies, levels, and members.</span></span>

<span data-ttu-id="77d3b-p111">*维*是来自多维数据库中的一种独立的数据类别，派生于您的业务实体。维通常包含用作数据库度量的查询条件的项目。</span><span class="sxs-lookup"><span data-stu-id="77d3b-p111">A *dimension* is an independent category of data from your multidimensional database, derived from your business entities. A dimension typically contains items to be used as query criteria for the measures of the database.</span></span>

<span data-ttu-id="77d3b-p112">*层次结构*是维度聚合的路径。一个维度可以有多种级别的粒度，这些粒度级别具有父子关系。层次结构定义这些级别之间的关系。</span><span class="sxs-lookup"><span data-stu-id="77d3b-p112">A *hierarchy* is a path of aggregation of a dimension. A dimension may have multiple levels of granularity, which have parent-child relationships. A hierarchy defines how these levels are related.</span></span>

<span data-ttu-id="77d3b-152">*级别*是层次结构中的聚合步骤。</span><span class="sxs-lookup"><span data-stu-id="77d3b-152">A *level* is a step of aggregation in a hierarchy.</span></span> <span data-ttu-id="77d3b-153">对于具有多种信息层的维，每层就是一个级别。</span><span class="sxs-lookup"><span data-stu-id="77d3b-153">For dimensions with multiple layers of information, each layer is a level.</span></span>

<span data-ttu-id="77d3b-154">*成员*是维中的数据项。</span><span class="sxs-lookup"><span data-stu-id="77d3b-154">A *member* is a data item in a dimension.</span></span> <span data-ttu-id="77d3b-155">通常，使用成员来创建标题或描述数据库度量。</span><span class="sxs-lookup"><span data-stu-id="77d3b-155">Typically, you create a caption or describe a measure of the database using members.</span></span>

<span data-ttu-id="77d3b-p115">多维数据集由 ADO MD 中的 [CubeDef](cubedef-object-ado-md.md) 对象表示。维、层次结构、级别和成员也由各自相应的 ADO MD 对象表示： [Dimension](dimension-object-ado-md.md)、[Hierarchy](hierarchy-object-ado-md.md)、[Level](level-object-ado-md.md) 和 [Member](member-object-ado-md.md)。</span><span class="sxs-lookup"><span data-stu-id="77d3b-p115">Cubes are represented by [CubeDef](cubedef-object-ado-md.md) objects in ADO MD. Dimensions, hierarchies, levels, and members are also represented by their corresponding ADO MD objects: [Dimension](dimension-object-ado-md.md), [Hierarchy](hierarchy-object-ado-md.md), [Level](level-object-ado-md.md), and [Member](member-object-ado-md.md).</span></span>

## <a name="dimensions"></a><span data-ttu-id="77d3b-158">Dimensions</span><span class="sxs-lookup"><span data-stu-id="77d3b-158">Dimensions</span></span>

<span data-ttu-id="77d3b-p116">多维数据集的维取决于您的业务实体和要在数据库中建模的数据类型。通常，每个维是一个用于选择数据的独立入口点或机制。</span><span class="sxs-lookup"><span data-stu-id="77d3b-p116">The dimensions of a cube depend on your business entities and types of data to be modeled in the database. Typically, each dimension is an independent entry point or mechanism for selecting data.</span></span>

<span data-ttu-id="77d3b-p117">例如，包含销售数据的多维数据集具有以下五个维：Salesperson、Geography、Time、Products 和 Measures。Measures 维包含实际的销售数据值，而其他维则表示对销售数据值进行分类和分组的方式。</span><span class="sxs-lookup"><span data-stu-id="77d3b-p117">For example, a cube containing sales data has the following five dimensions: Salesperson, Geography, Time, Products, and Measures. The Measures dimension contains actual sales data values, while the other dimensions represent ways to categorize and group the sales data values.</span></span>

<span data-ttu-id="77d3b-163">Geography 维具有以下成员集：</span><span class="sxs-lookup"><span data-stu-id="77d3b-163">The Geography dimension has the following set of members:</span></span>

```text 
 
{All, North America, Europe, Canada, USA, UK, Germany, Canada-West, 
Canada-East, USA-NW, USA-SW, USA-NE, USA-SE, England, Scotland,  
Wales,Ireland, Germany-North, Germany-South, Ottawa, Toronto,  
Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston,  
Shreveport, Miami, Boston, New York, London, Dover, Glasgow,  
Edinburgh, Cardiff, Pembroke, Belfast, Berlin,  
Hamburg, Munich, Stuttgart} 
```

## <a name="hierarchies"></a><span data-ttu-id="77d3b-164">Hierarchies</span><span class="sxs-lookup"><span data-stu-id="77d3b-164">Hierarchies</span></span>

<span data-ttu-id="77d3b-p118">层次结构定义可以对维的级别进行“汇总”或分组的方式。一个维可以有多个层次结构。</span><span class="sxs-lookup"><span data-stu-id="77d3b-p118">Hierarchies define the ways in which the levels of a dimension can be "rolled up" or grouped. A dimension can have more than one hierarchy.</span></span>

## <a name="levels"></a><span data-ttu-id="77d3b-167">Levels</span><span class="sxs-lookup"><span data-stu-id="77d3b-167">Levels</span></span>

<span data-ttu-id="77d3b-168">在上图说明的 Geography 维示例中，每个框代表层次结构中的一个级别。</span><span class="sxs-lookup"><span data-stu-id="77d3b-168">In the example Geography dimension pictured in the previous figure, each box represents a level in the hierarchy.</span></span>

<span data-ttu-id="77d3b-169">每个级别都有一组成员，如下所示：</span><span class="sxs-lookup"><span data-stu-id="77d3b-169">Each level has a set of members, as follows:</span></span>

- <span data-ttu-id="77d3b-170">The World = {All}
</span><span class="sxs-lookup"><span data-stu-id="77d3b-170">The World = {All}</span></span>

- <span data-ttu-id="77d3b-171">洲 = {北美、欧洲}</span><span class="sxs-lookup"><span data-stu-id="77d3b-171">Continents = {North America, Europe}</span></span>

- <span data-ttu-id="77d3b-172">国家/地区 = {加拿大, 美国, 英国, 德国}</span><span class="sxs-lookup"><span data-stu-id="77d3b-172">Countries = {Canada, USA, UK, Germany}</span></span>

- <span data-ttu-id="77d3b-173">地区 = {加拿大-东部, 加拿大-西部, 美国-NE, 美国-NW, 美国-SE, 美国-SW, 英国, 爱尔兰, 苏格兰, 威尔士, 德国-北部, 德国-南部}</span><span class="sxs-lookup"><span data-stu-id="77d3b-173">Regions = {Canada-East, Canada-West, USA-NE, USA-NW, USA-SE, USA-SW, England, Ireland, Scotland, Wales, Germany-North, Germany-South}</span></span>

- <span data-ttu-id="77d3b-174">城市 = {渥太华、多伦多、范 Boise、卡尔加里、西雅图、、洛杉矶、休斯顿、Shreveport、迈阿密、波士顿、纽约、伦敦、Dover、Glasgow、爱丁堡、Cardiff、Pembroke、Belfast、柏林、Hamburg、慕尼黑、斯图加特}</span><span class="sxs-lookup"><span data-stu-id="77d3b-174">Cities = {Ottawa, Toronto, Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston, Shreveport, Miami, Boston, New York, London, Dover, Glasgow, Edinburgh, Cardiff, Pembroke, Belfast, Berlin, Hamburg, Munich, Stuttgart}</span></span>

## <a name="members"></a><span data-ttu-id="77d3b-175">Members</span><span class="sxs-lookup"><span data-stu-id="77d3b-175">Members</span></span>

<span data-ttu-id="77d3b-p119">位于层次结构叶级别的成员没有子级，且位于根级别的成员没有父级。所有其他成员具有至少一个父级和至少一个子级。例如，Geography 维中的层次结构树的部分遍历会产生以下父子关系：</span><span class="sxs-lookup"><span data-stu-id="77d3b-p119">Members at the leaf level of a hierarchy have no children, and members at the root level have no parent. All other members have at least one parent and at least one child. For example, a partial traversal of the hierarchy tree in the Geography dimension yields the following parent-child relationships:</span></span>

- <span data-ttu-id="77d3b-179">各种(的父级){欧洲, 北美}</span><span class="sxs-lookup"><span data-stu-id="77d3b-179">{All} (parent of) {Europe, North America}</span></span>

- <span data-ttu-id="77d3b-180">{北美}(的父级){加拿大, 美国}</span><span class="sxs-lookup"><span data-stu-id="77d3b-180">{North America} (parent of) {Canada, USA}</span></span>

- <span data-ttu-id="77d3b-181">特区(的父级){美国-NE, 美国-NW, 美国-SE, 美国-SW}</span><span class="sxs-lookup"><span data-stu-id="77d3b-181">{USA} (parent of) {USA-NE, USA-NW, USA-SE, USA-SW}</span></span>

- <span data-ttu-id="77d3b-182">{美国-NW}(的父级){Boise, 西雅图}</span><span class="sxs-lookup"><span data-stu-id="77d3b-182">{USA-NW} (parent of) {Boise, Seattle}</span></span>

<span data-ttu-id="77d3b-183">可以合并每个维的一个或多个层次结构的成员。</span><span class="sxs-lookup"><span data-stu-id="77d3b-183">Members can be consolidated along one or more hierarchies per dimension.</span></span>

<span data-ttu-id="77d3b-184">本示例还演示了另一个特征: 一年的第一周层次结构中的某些成员不会出现在任何级别的年季度层次结构中。</span><span class="sxs-lookup"><span data-stu-id="77d3b-184">This example also illustrates another characteristic: some members of the Week level of the Year-Week hierarchy do not appear in any level of the Year-Quarter hierarchy.</span></span> <span data-ttu-id="77d3b-185">这样，层次结构就不需要包括维的所有成员。</span><span class="sxs-lookup"><span data-stu-id="77d3b-185">Thus, a hierarchy need not include all members of a dimension.</span></span>

