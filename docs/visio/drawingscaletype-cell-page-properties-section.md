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
description: 确定在“页面设置”对话框（单击“开始”选项卡上的“页面设置”箭头）中所选的绘图缩放比例。
ms.openlocfilehash: d1c1c00ffe025c566646a1f8b9fe034732ad86a8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428737"
---
# <a name="drawingscaletype-cell-page-properties-section"></a>DrawingScaleType 单元格（“Page Properties”内容）

确定在 **“页面设置”** 对话框（单击 **“开始”** 选项卡上的 **“页面设置”** 箭头）中所选的绘图缩放比例。 
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 无比例  <br/> |**visNoScale** <br/> |
| 1  <br/> | 结构比例  <br/> |**visArchitectural** <br/> |
| 双面  <br/> | 土木工程比例  <br/> |**visEngineering** <br/> |
| 第三章  <br/> | 自定义缩放比例  <br/> |**visScaleCustom** <br/> |
| 4  <br/> | 多重  <br/> |**visScaleMetric** <br/> |
| 5  <br/> | 机械工程比例  <br/> |**visScaleMechanical** <br/> |
   
## <a name="remarks"></a>说明

若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DrawingScaleType 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | DrawingScaleType  <br/> |
   
若要从某个程序按索引获取对 DrawingScaleType 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageDrawScaleType** <br/> |
   

