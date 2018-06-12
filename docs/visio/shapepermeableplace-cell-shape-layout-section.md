---
title: ShapePermeablePlace 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm885
localization_priority: Normal
ms.assetid: b647cbb5-2769-068d-bbda-2dc983c47ac9
description: 确定是否可放置形状时，可放置在形状的顶部排放形状在配置布局对话框 （在设计选项卡上的布局组中，单击重新布局页面，然后单击更多布局选项）。
ms.openlocfilehash: 1873575eb4322d31f81c0dd34557c6167750ce82
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781264"
---
# <a name="shapepermeableplace-cell-shape-layout-section"></a>ShapePermeablePlace 单元格（“Shape Layout”内容）

确定是否可放置形状时，可放置在形状的顶部排放形状在**配置布局**对话框 （**设计**选项卡上，在**布局**组中，单击**Re 布局页**，然后单击**更多布局选项**).
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |使形状能够放置在某个形状的顶部。  <br/> |
|FALSE  <br/> |使形状不能放置在某个形状的顶部。  <br/> |
   
## <a name="remarks"></a>注解

您还可以在**行为**对话框中的**位置**选项卡上设置此单元格的值 （与选定形状，在[开发人员](run-in-developer-mode-display-the-developer-tab.md)选项卡的**形状设计**组中，单击**行为**，，然后单击**位置**选项卡). 
  
在 Visio 2000 之前的版本中，您可以使用“Miscellaneous”内容中的 ObjInteract 单元格设置此行为。
  
若要获取对 ShapePermeablePlace 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShapePermeablePlace  <br/> |
   
若要从某个程序按索引获取对 ShapePermeablePlace 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLOPermeablePlace** <br/> |
   

