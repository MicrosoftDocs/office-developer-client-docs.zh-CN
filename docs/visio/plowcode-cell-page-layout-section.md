---
title: PlowCode 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251660
localization_priority: Normal
ms.assetid: e43f3d29-7def-d36e-ac64-62f0a389d415
description: 确定在绘图页上将一个可放置形状放到另一个可放置形状旁边时，可放置形状是否移走。
ms.openlocfilehash: 4ea85ddbaf7662305a2a82fc7f0b814019624841
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420351"
---
# <a name="plowcode-cell-page-layout-section"></a>PlowCode 单元格（“Page Layout”内容）

确定在绘图页上将一个可放置形状放到另一个可放置形状旁边时，可放置形状是否移走。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |不移动形状  <br/> |**visPLOPlowNone** <br/> |
|1  <br/> |移动形状  <br/> |**visPLOPlowAll** <br/> |
   
## <a name="remarks"></a>备注

您还可以在"设计"选项卡上 (的"页面设置"对话框中的"布局和传送"选项卡上设置此单元格的值，使用"拖放时移走其他形状"复选框单击"页面设置"箭头) 。  
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PlowCode 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |PlowCode  <br/> |
   
若要从某个程序按索引获取对 PlowCode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLOPlowCode** <br/> |
   

