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
# <a name="overview-of-multidimensional-schemas-and-data"></a>多维架构和数据概述

**适用于**：Access 2013、Office 2013

## <a name="understanding-multidimensional-schemas"></a>了解多维架构

ADO MD 中的中心元数据对象是*多维数据集*，由相关维、层次结构、级别和成员的结构化集合构成。

*维*是来自多维数据库中的一种独立的数据类别，派生于您的业务实体。维通常包含用作数据库度量的查询条件的项目。

*层次结构*是维度聚合的路径。一个维度可以有多种级别的粒度，这些粒度级别具有父子关系。层次结构定义这些级别之间的关系。

*级别*是层次结构中的聚合步骤。 对于具有多种信息层的维，每层就是一个级别。

*成员*是维中的数据项。 通常，使用成员来创建标题或描述数据库度量。

多维数据集由 ADO MD 中的 [CubeDef](cubedef-object-ado-md.md) 对象表示。维、层次结构、级别和成员也由各自相应的 ADO MD 对象表示： [Dimension](dimension-object-ado-md.md)、[Hierarchy](hierarchy-object-ado-md.md)、[Level](level-object-ado-md.md) 和 [Member](member-object-ado-md.md)。

## <a name="dimensions"></a>Dimensions

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

## <a name="hierarchies"></a>Hierarchies

层次结构定义可以对维的级别进行“汇总”或分组的方式。一个维可以有多个层次结构。

## <a name="levels"></a>Levels

在上图说明的 Geography 维示例中，每个框代表层次结构中的一个级别。

每个级别都有一组成员，如下所示：

  - The World = {All}


  - 洲 = {北美、欧洲}

  - 国家/地区 = {加拿大, 美国, 英国, 德国}

  - 地区 = {加拿大-东部, 加拿大-西部, 美国-NE, 美国-NW, 美国-SE, 美国-SW, 英国, 爱尔兰, 苏格兰, 威尔士, 德国-北部, 德国-南部}

  - 城市 = {渥太华、多伦多、范 Boise、卡尔加里、西雅图、、洛杉矶、休斯顿、Shreveport、迈阿密、波士顿、纽约、伦敦、Dover、Glasgow、爱丁堡、Cardiff、Pembroke、Belfast、柏林、Hamburg、慕尼黑、斯图加特}

## <a name="members"></a>Members

位于层次结构叶级别的成员没有子级，且位于根级别的成员没有父级。所有其他成员具有至少一个父级和至少一个子级。例如，Geography 维中的层次结构树的部分遍历会产生以下父子关系：

- 各种(的父级){欧洲, 北美}
- {北美}(的父级){加拿大, 美国}
- 特区(的父级){美国-NE, 美国-NW, 美国-SE, 美国-SW}
- {美国-NW}(的父级){Boise, 西雅图}

可以合并每个维的一个或多个层次结构的成员。

本示例还演示了另一个特征: 一年的第一周层次结构中的某些成员不会出现在任何级别的年季度层次结构中。 这样，层次结构就不需要包括维的所有成员。

## <a name="understanding-multidimensional-schemas"></a>了解多维架构

ADO MD 中的中心元数据对象是*多维数据集*，由相关维、层次结构、级别和成员的结构化集合构成。

*维*是来自多维数据库中的一种独立的数据类别，派生于您的业务实体。维通常包含用作数据库度量的查询条件的项目。

*层次结构*是维度聚合的路径。一个维度可以有多种级别的粒度，这些粒度级别具有父子关系。层次结构定义这些级别之间的关系。

*级别*是层次结构中的聚合步骤。 对于具有多种信息层的维，每层就是一个级别。

*成员*是维中的数据项。 通常，使用成员来创建标题或描述数据库度量。

多维数据集由 ADO MD 中的 [CubeDef](cubedef-object-ado-md.md) 对象表示。维、层次结构、级别和成员也由各自相应的 ADO MD 对象表示： [Dimension](dimension-object-ado-md.md)、[Hierarchy](hierarchy-object-ado-md.md)、[Level](level-object-ado-md.md) 和 [Member](member-object-ado-md.md)。

## <a name="dimensions"></a>Dimensions

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

## <a name="hierarchies"></a>Hierarchies

层次结构定义可以对维的级别进行“汇总”或分组的方式。一个维可以有多个层次结构。

## <a name="levels"></a>Levels

在上图说明的 Geography 维示例中，每个框代表层次结构中的一个级别。

每个级别都有一组成员，如下所示：

- The World = {All}


- 洲 = {北美、欧洲}

- 国家/地区 = {加拿大, 美国, 英国, 德国}

- 地区 = {加拿大-东部, 加拿大-西部, 美国-NE, 美国-NW, 美国-SE, 美国-SW, 英国, 爱尔兰, 苏格兰, 威尔士, 德国-北部, 德国-南部}

- 城市 = {渥太华、多伦多、范 Boise、卡尔加里、西雅图、、洛杉矶、休斯顿、Shreveport、迈阿密、波士顿、纽约、伦敦、Dover、Glasgow、爱丁堡、Cardiff、Pembroke、Belfast、柏林、Hamburg、慕尼黑、斯图加特}

## <a name="members"></a>Members

位于层次结构叶级别的成员没有子级，且位于根级别的成员没有父级。所有其他成员具有至少一个父级和至少一个子级。例如，Geography 维中的层次结构树的部分遍历会产生以下父子关系：

- 各种(的父级){欧洲, 北美}

- {北美}(的父级){加拿大, 美国}

- 特区(的父级){美国-NE, 美国-NW, 美国-SE, 美国-SW}

- {美国-NW}(的父级){Boise, 西雅图}

可以合并每个维的一个或多个层次结构的成员。

本示例还演示了另一个特征: 一年的第一周层次结构中的某些成员不会出现在任何级别的年季度层次结构中。 这样，层次结构就不需要包括维的所有成员。

