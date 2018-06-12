---
title: DrawingScaleType 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm270
localization_priority: Normal
ms.assetid: 5d4f1cf8-bc1f-07b8-1da5-7253808e337e
description: 确定在页面设置对话框中选中的绘图缩放比例 （单击主页选项卡上的页面设置箭头）。
ms.openlocfilehash: b93bd95a30fe5a8a5de15a8e5ea104279cf1bcda
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780154"
---
# <a name="drawingscaletype-cell-page-properties-section"></a>DrawingScaleType 单元格（“Page Properties”内容）

确定在**页面设置**对话框中选中的绘图缩放比例 （单击**主页**选项卡上的**页面设置**箭头）。 
  
|**值**|**说明**|**自动化常量**|
|:-----|:-----|:-----|
| 0  <br/> | 无比例  <br/> |**visNoScale** <br/> |
| 1  <br/> | 结构比例  <br/> |**visArchitectural** <br/> |
| 2  <br/> | 土木工程比例  <br/> |**visEngineering** <br/> |
| 3  <br/> | 自定义缩放比例  <br/> |**visScaleCustom** <br/> |
| 4  <br/> | 公制  <br/> |**visScaleMetric** <br/> |
| 5  <br/> | 机械工程比例  <br/> |**visScaleMechanical** <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 DrawingScaleType 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | DrawingScaleType  <br/> |
   
若要从某个程序按索引获取对 DrawingScaleType 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageDrawScaleType** <br/> |
   

