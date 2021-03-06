---
title: LineJumpCode 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm540
localization_priority: Normal
ms.assetid: 56f9043d-a632-65df-c710-45867cce1627
description: 确定要向其添加跨线的连接线。
ms.openlocfilehash: 7b5b8c8f1de160a4dc766d30a5f518c5653c270b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416249"
---
# <a name="linejumpcode-cell-page-layout-section"></a>LineJumpCode 单元格（“Page Layout”内容）

确定要向其添加跨线的连接线。
  
|**值**|**要向其添加跨线的连接线**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |None  <br/> |**visPLOJumpNone** <br/> |
|1  <br/> |水平线  <br/> |**visPLOJumpHorizontal** <br/> |
|2  <br/> |垂直线  <br/> |**visPLOJumpVertical** <br/> |
|3  <br/> |最后一个放置的线条  <br/> |**visPLOJumpLastRouted** <br/> |
|4   <br/> |z -order (顶部  *形状最后显示的* )   <br/> |**visPLOJumpDisplayOrder** <br/> |
|5   <br/> |z-order (底部的第一个显示线条)   <br/> |**visPLOJumpReverseDisplayOrder** <br/> |
   
## <a name="remarks"></a>备注

还可以在 **“页面设置”** 对话框中的 **“布局与排列”** 选项卡（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，然后单击 **“布局与排列”**）上设置此单元格的值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineJumpCode 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LineJumpCode  <br/> |
   
若要从某个程序按索引获取对 LineJumpCode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLOJumpCode** <br/> |
   

