---
title: ResizeMode 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251203
localization_priority: Normal
ms.assetid: 49816e46-fa83-3ee4-1451-9c85fbd0f519
description: 显示形状的当前调整大小行为设置。
ms.openlocfilehash: 7e9080fcd4604e2dbdc1dae31992f05e5b512213
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421961"
---
# <a name="resizemode-cell-shape-transform-section"></a>ResizeMode 单元格（“Shape Transform”内容）

显示形状的当前调整大小行为设置。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |使用组合的设置。  <br/> |**visXFormResizeDontCare** <br/> |
|1  <br/> |仅重定位。  <br/> |**visXFormResizeSpread** <br/> |
|2  <br/> |和组合一起缩放。  <br/> |**visXFormResizeScale** <br/> |
   
## <a name="remarks"></a>备注

您还可以在"开发工具"选项卡上"行为" ("行为"选项卡上的"形状设计"[](run-in-developer-mode-display-the-developer-tab.md)**组中，单击**"行为") 。   若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ResizeMode 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ResizeMode  <br/> |
   
若要从某个程序按索引获取对 ResizeMode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowXFormOut** <br/> |
|单元格索引：  <br/> |**visXFormResizeMode** <br/> |
   

