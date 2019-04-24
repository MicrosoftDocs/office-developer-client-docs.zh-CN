---
title: ConnectorSchemeIndex 单元格 ("主题属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 48ab98bd-2966-443c-b3db-befeb271550f
description: 确定应用于形状的主题的连接器方案, 以整数形式表示。
ms.openlocfilehash: 77d16632db63d187477ba62a1a6f4b9319e156fc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319710"
---
# <a name="connectorschemeindex-cell-theme-properties-section"></a>ConnectorSchemeIndex 单元格 ("主题属性" 部分)

确定应用于形状的主题的连接器方案, 以整数形式表示。 
  
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**ConnectorSchemeIndex**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ConnectorSchemeIndex  <br/> |
   
若要从某个程序按索引获取对**ConnectorSchemeIndex**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowThemeProperties** <br/> |
| 单元格索引：  <br/> |* * visConnectorSchemeIndex * * <br/> |
   

