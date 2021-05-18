---
title: DisplayMode 单元格（“Group Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251623
localization_priority: Normal
ms.assetid: e6d72529-aa03-e94b-130c-79ed04336299
description: 确定组合形状及其成员的显示方式。
ms.openlocfilehash: a49d7a38eac75a2845de0ca3ad22f7cbf79a63df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413183"
---
# <a name="displaymode-cell-group-properties-section"></a>DisplayMode 单元格（“Group Properties”内容）

确定组合形状及其成员的显示方式。
  
|**值**|**显示模式**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |隐藏组合形状和文本。  <br/> |**visGrpDispModeNone** <br/> |
|1  <br/> |将组合形状显示在成员形状后面。  <br/> |**visGrpDispModeBack** <br/> |
|2  <br/> |将组合形状显示在成员形状的前面。  <br/> |**visGrpDispModeFront** <br/> |
   
## <a name="remarks"></a>备注

您还可以设置此值，方法是选择该组，单击"开发工具"选项卡上的"形状设计"组 [](run-in-developer-mode-display-the-developer-tab.md)上的"行为"，然后从"组数据"**列表中选择** 显示模式。  
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DisplayMode 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |DisplayMode  <br/> |
   
要从某个程序按索引获取对 DisplayMode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowGroup** <br/> |
|单元格索引：  <br/> |**visGroupDisplayMode** <br/> |
   

