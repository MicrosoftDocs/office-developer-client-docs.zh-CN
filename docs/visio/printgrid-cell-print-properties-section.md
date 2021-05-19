---
title: PrintGrid 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033794
localization_priority: Normal
ms.assetid: 0504ff7f-2274-7ae3-1f4b-a3d890dbd79a
description: 指定在打印文档页面时是否打印网格。
ms.openlocfilehash: 9b98999cd02fa6a47ec8564bbd7337ecf8637306
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433204"
---
# <a name="printgrid-cell-print-properties-section"></a>PrintGrid 单元格（“Print Properties”内容）

指定在打印文档页面时是否打印网格。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |在打印此页时显示网格。  <br/> |
|FALSE  <br/> |在打印此页时不显示网格（默认值）。  <br/> |
   
## <a name="remarks"></a>备注

此值对应于 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头）中 **“打印设置”** 选项卡上的 **“网格线”** 复选框。与颜色（打印出来的效果为灰色）不同的是，打印出来的网格与您在 Microsoft Visio 绘图窗口中看到的网格相同。 
  
您可以选择是否逐页打印网格。 还可以在"视图"选项卡上的"标尺网格"对话框 (中，单击"在页面处于活动状态时显示网格) 按页定义网格的样式。 **&amp;** 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PrintGrid 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |PrintGrid  <br/> |
   
若要从某个程序按索引获取对 PrintGrid 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPrintProperties** <br/> |
|单元格索引：  <br/> |**visPrintPropertiesPrintGrid** <br/> |
   

