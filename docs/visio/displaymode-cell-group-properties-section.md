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
ms.openlocfilehash: 086685b47d8eaf170a8722f7cd00545230541e79
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780100"
---
# <a name="displaymode-cell-group-properties-section"></a>DisplayMode 单元格（“Group Properties”部分）

确定组合形状及其成员的显示方式。
  
|**值**|**显示模式**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |隐藏组合形状和文本。  <br/> |**visGrpDispModeNone** <br/> |
|1  <br/> |将组合形状显示在成员形状后面。  <br/> |**visGrpDispModeBack** <br/> |
|2  <br/> |将组合形状显示在成员形状的前面。  <br/> |**visGrpDispModeFront** <br/> |
   
## <a name="remarks"></a>说明

您还可以设置此值选择该组合，单击**行为**在[开发人员](run-in-developer-mode-display-the-developer-tab.md)选项卡上的**形状设计**组，然后从**组数据**列表中选择的显示模式。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DisplayMode 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |DisplayMode  <br/> |
   
若要从某个程序按索引获取对 DisplayMode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowGroup** <br/> |
|单元格索引：  <br/> |**visGroupDisplayMode** <br/> |
   

