---
title: Type / C 单元格（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251723
localization_priority: Normal
ms.assetid: 2264d026-2041-3855-2b23-553ce67ae69d
description: 确定连接点类型。
ms.openlocfilehash: a73554d9f3a3bce6a039689d2c0b192a1c5b69aa
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359582"
---
# <a name="type--c-cell-connection-points-section"></a>Type / C 单元格（“Connection Points”内容）

确定连接点类型。
  
|**值**|**类型**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |拖动  <br/> |**visCnnctTypeInward** <br/> |
|1  <br/> |提  <br/> |**visCnnctTypeOutward** <br/> |
|双面  <br/> |向&amp;外  <br/> |**visCnnctTypeInwardOutward** <br/> |
   
## <a name="remarks"></a>注解

您也可以通过选择 **“连接线”** 工具，再选择一个形状，然后右键单击连接点，来设置连接点类型。若要完成此操作，需要在[开发工具](run-in-developer-mode-display-the-developer-tab.md)模式下运行。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Type / C 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |连接。键入 [ *i* ] where ** = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 Type / C 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionConnectionPts** <br/> |
|行索引：  <br/> |**visRowConnectionPts** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visCnnctType**(非扩展行)**visCnnctC**(扩展行)  <br/> |
   
有关扩展行和非扩展行的信息，请参见 Connection Points 行。
  

