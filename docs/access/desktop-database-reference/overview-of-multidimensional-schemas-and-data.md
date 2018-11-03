---
title: 多维架构和数据概述
TOCTitle: Overview of Multidimensional Schemas and Data
ms:assetid: a963e993-b7bf-eeb4-ecd5-d6fe43cf4bb5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249784(v=office.15)
ms:contentKeyID: 48546923
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 67bdcdbaa525039f544a7d45cb4411faeee297e8
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937027"
---
# <a name="overview-of-multidimensional-schemas-and-data"></a>多维架构和数据概述


**适用于**： Access 2013、 Office 2013

## <a name="understanding-multidimensional-schemas"></a>了解多维架构

ADO MD 中的中心元数据对象是*多维数据集*，由相关维、层次结构、级别和成员的结构化集合构成。

*维度*是独立的来自多维数据库，从您的业务实体派生的数据类别。 维通常包含用作数据库度量的查询条件的项目。

*层次结构*是聚合一个维度的路径。 一个维度可以有多种级别的粒度，这些粒度级别具有父子关系。 层次结构定义这些级别之间的关系。

*级别*为聚合层次结构中的步骤。 对于具有多种信息层的维，每层就是一个级别。

*成员*是维度中数据的项目。 通常，使用成员来创建标题或描述数据库度量。

多维数据集由 ADO MD 中的 [CubeDef](cubedef-object-ado-md.md) 对象表示。维、层次结构、级别和成员也由各自相应的 ADO MD 对象表示： [Dimension](dimension-object-ado-md.md)、[Hierarchy](hierarchy-object-ado-md.md)、[Level](level-object-ado-md.md) 和 [Member](member-object-ado-md.md)。

## <a name="dimensions"></a>维度

多维数据集的维取决于您的业务实体和要在数据库中建模的数据类型。通常，每个维是一个用于选择数据的独立入口点或机制。

例如，包含销售数据的多维数据集具有以下五个维：Salesperson、Geography、Time、Products 和 Measures。Measures 维包含实际的销售数据值，而其他维则表示对销售数据值进行分类和分组的方式。

Geography 维具有以下成员集：

```text
 
{All, North America, Europe, Canada, USA, UK, Germany, Canada-West, 
Canada-East, USA-NW, USA-SW, USA-NE, USA-SE, England, Scotland,  
Wales,Ireland, Germany-North, Germany-South, Ottawa, Toronto,  
Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston,  
Shreveport, Miami, Boston, New York, London, Dover, Glasgow,  
Edinburgh, Cardiff, Pembroke, Belfast, Berlin,  
Hamburg, Munich, Stuttgart} 
```

## <a name="hierarchies"></a>层次结构

层次结构定义可以对维的级别进行"汇总"或分组的方式。一个维可以有多个层次结构。

## <a name="levels"></a>级别

在上图说明的 Geography 维示例中，每个框代表层次结构中的一个级别。

每个级别都有一组成员，如下所示：

  - The World = {All}


  - Continents = {North America, Europe}


  - Countries = {Canada, USA, UK, Germany}


  - Regions = {Canada-East, Canada-West, USA-NE, USA-NW, USA-SE, USA-SW, England, Ireland, Scotland, Wales, Germany-North, Germany-South}


  - Cities = {Ottawa, Toronto, Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston, Shreveport, Miami, Boston, New York, London, Dover, Glasgow, Edinburgh, Cardiff, Pembroke, Belfast, Berlin, Hamburg, Munich, Stuttgart}


## <a name="members"></a>成员

位于层次结构叶级别的成员没有子级，且位于根级别的成员没有父级。所有其他成员具有至少一个父级和至少一个子级。例如，Geography 维中的层次结构树的部分遍历会产生以下父子关系：

- {所有}（的父对象）{欧洲、 北美洲}
- {北美}（的父对象）{加拿大，美国}
- {USA}（的父对象）{USA NE，美国-NW，美国 SE，美国-软件}
- {USA NW}（的父对象）{博伊西，西雅图}

可以合并每个维的一个或多个层次结构的成员。

此示例还演示了其他特征： 年周层次结构的周级别的某些成员不出现在任何年季度层次结构的级别。 这样，层次结构就不需要包括维的所有成员。

## <a name="understanding-multidimensional-schemas"></a>了解多维架构

ADO MD 中的中心元数据对象是*多维数据集*，由相关维、层次结构、级别和成员的结构化集合构成。

*维度*是独立的来自多维数据库，从您的业务实体派生的数据类别。 维通常包含用作数据库度量的查询条件的项目。

*层次结构*是聚合一个维度的路径。 一个维度可以有多种级别的粒度，这些粒度级别具有父子关系。 层次结构定义这些级别之间的关系。

*级别*为聚合层次结构中的步骤。 对于具有多种信息层的维，每层就是一个级别。

*成员*是维度中数据的项目。 通常，使用成员来创建标题或描述数据库度量。

多维数据集由 ADO MD 中的 [CubeDef](cubedef-object-ado-md.md) 对象表示。维、层次结构、级别和成员也由各自相应的 ADO MD 对象表示： [Dimension](dimension-object-ado-md.md)、[Hierarchy](hierarchy-object-ado-md.md)、[Level](level-object-ado-md.md) 和 [Member](member-object-ado-md.md)。

## <a name="dimensions"></a>维度

多维数据集的维取决于您的业务实体和要在数据库中建模的数据类型。通常，每个维是一个用于选择数据的独立入口点或机制。

例如，包含销售数据的多维数据集具有以下五个维：Salesperson、Geography、Time、Products 和 Measures。Measures 维包含实际的销售数据值，而其他维则表示对销售数据值进行分类和分组的方式。

Geography 维具有以下成员集：

```text 
 
{All, North America, Europe, Canada, USA, UK, Germany, Canada-West, 
Canada-East, USA-NW, USA-SW, USA-NE, USA-SE, England, Scotland,  
Wales,Ireland, Germany-North, Germany-South, Ottawa, Toronto,  
Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston,  
Shreveport, Miami, Boston, New York, London, Dover, Glasgow,  
Edinburgh, Cardiff, Pembroke, Belfast, Berlin,  
Hamburg, Munich, Stuttgart} 
```

## <a name="hierarchies"></a>层次结构

层次结构定义可以对维的级别进行"汇总"或分组的方式。一个维可以有多个层次结构。

## <a name="levels"></a>级别

在上图说明的 Geography 维示例中，每个框代表层次结构中的一个级别。

每个级别都有一组成员，如下所示：

- The World = {All}


- Continents = {North America, Europe}


- Countries = {Canada, USA, UK, Germany}


- Regions = {Canada-East, Canada-West, USA-NE, USA-NW, USA-SE, USA-SW, England, Ireland, Scotland, Wales, Germany-North, Germany-South}


- Cities = {Ottawa, Toronto, Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston, Shreveport, Miami, Boston, New York, London, Dover, Glasgow, Edinburgh, Cardiff, Pembroke, Belfast, Berlin, Hamburg, Munich, Stuttgart}


## <a name="members"></a>成员

位于层次结构叶级别的成员没有子级，且位于根级别的成员没有父级。所有其他成员具有至少一个父级和至少一个子级。例如，Geography 维中的层次结构树的部分遍历会产生以下父子关系：

- {所有}（的父对象）{欧洲、 北美洲}

- {北美}（的父对象）{加拿大，美国}

- {USA}（的父对象）{USA NE，美国-NW，美国 SE，美国-软件}

- {USA NW}（的父对象）{博伊西，西雅图}

可以合并每个维的一个或多个层次结构的成员。

此示例还演示了其他特征： 年周层次结构的周级别的某些成员不出现在任何年季度层次结构的级别。 这样，层次结构就不需要包括维的所有成员。

