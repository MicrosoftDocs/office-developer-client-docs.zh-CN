---
title: DrawingSizeType 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm275
localization_priority: Normal
ms.assetid: 7fe270e8-0dff-bf1f-dfc0-c0608af79f59
description: 确定绘图的大小。
ms.openlocfilehash: 33c85b6c2f0587654038eaec1a9490ca8bd8301b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425447"
---
# <a name="drawingsizetype-cell-page-properties-section"></a>DrawingSizeType 单元格（“Page Properties”内容）

确定绘图的大小。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |同于打印机  <br/> |**visPrintSetup** <br/> |
|1  <br/> |调整页面大小以适合绘图内容  <br/> |**visTight** <br/> |
|双面  <br/> |标准  <br/> |**visStandard** <br/> |
|第三章  <br/> |自定义页大小  <br/> |**visCustom** <br/> |
|4  <br/> |自定义缩放比例的绘图大小  <br/> |**visLogical** <br/> |
|5  <br/> |公制 (ISO)  <br/> |**visDSMetric** <br/> |
|型  <br/> |ANSI 工程  <br/> |**visDSEngr** <br/> |
|步  <br/> |ANSI 结构  <br/> |**visDSArch** <br/> |
   
## <a name="remarks"></a>说明

若要设置绘图大小，请使用 **“页面设置”** 对话框（单击 **“设计”** 选项卡上的 **“页面设置”** 箭头）或用鼠标手动调整页面大小。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DrawingSizeType 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |DrawingSizeType  <br/> |
   
若要从某个程序按索引获取对 DrawingSizeType 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPage** <br/> |
|单元格索引：  <br/> |**visPageDrawSizeType** <br/> |
   

