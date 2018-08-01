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
ms.openlocfilehash: e180ce679f280cbccbda80b67170f2f26473bd8c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780896"
---
# <a name="plowcode-cell-page-layout-section"></a>PlowCode 单元格（“Page Layout”部分）

确定在绘图页上将一个可放置形状放到另一个可放置形状旁边时，可放置形状是否移走。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |不移动形状  <br/> |**visPLOPlowNone** <br/> |
|1  <br/> |移动形状  <br/> |**visPLOPlowAll** <br/> |
   
## <a name="remarks"></a>说明

您还可以在**页面设置**对话框中**布局和路由**选项卡上设置此单元格的值 （**设计**选项卡中，单击**页面设置**箭头） 通过使用**放下时移其他形状**复选框。 
  
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
   

