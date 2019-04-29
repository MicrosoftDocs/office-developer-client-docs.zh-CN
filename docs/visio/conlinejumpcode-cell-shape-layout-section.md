---
title: ConLineJumpCode 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251652
localization_priority: Normal
ms.assetid: af85588e-8e83-5168-7a8c-d7e8b4af5c27
description: 确定连接线何时跨线。
ms.openlocfilehash: 28bf506b8d3729fefec438d259746661fd28586e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421618"
---
# <a name="conlinejumpcode-cell-shape-layout-section"></a>ConLineJumpCode 单元格（“Shape Layout”内容）

确定连接线何时跨线。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |按照页面上指定的那样：在 **“设计”** 选项卡上，单击 **“页面设置”** 组中的箭头，然后单击 **“布局与排列”** 选项卡，查看页面规格  <br/> |**visSLOJumpDefault** <br/> |
|1  <br/> |Never  <br/> |**visSLOJumpNever** <br/> |
|双面  <br/> |Always  <br/> |**visSLOJumpAlways** <br/> |
|第三章  <br/> |其他连接线跨线  <br/> |**visSLOJumpOther** <br/> |
|4  <br/> |两条连接线都不跨线  <br/> |**visSLOJumpNeither** <br/> |
   
## <a name="remarks"></a>说明

您还可以通过以下方法设置此单元格的值: 选择动态连接线, 在 "[开发工具](run-in-developer-mode-display-the-developer-tab.md)" 选项卡上的 "**形状设计**" 组中单击 "**行为**", 然后单击 "**连接线**" 选项卡。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ConLineJumpCode 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ConLineJumpCode  <br/> |
   
若要从某个程序按索引获取对 ConLineJumpCode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLOJumpCode** <br/> |
   

