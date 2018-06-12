---
title: LineJumpFactorY 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm550
localization_priority: Normal
ms.assetid: 5a14be0d-9e3c-23c4-7782-bda5470d1243
description: 确定页中垂直动态连接线上的跨线的大小（相对于 LineToLineY 单元格的值）。该单元格的值范围可介于 0 到 10 之间，但建议使用 0 到 1 之间的小数值。
ms.openlocfilehash: deba4c27585644604e7bac1dbfe284bc3977835e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780590"
---
# <a name="linejumpfactory-cell-page-layout-section"></a>LineJumpFactorY 单元格（“Page Layout”内容）

确定页中垂直动态连接线上的跨线的大小（相对于 LineToLineY 单元格的值）。该单元格的值范围可介于 0 到 10 之间，但建议使用 0 到 1 之间的小数值。
  
## <a name="remarks"></a>注解

您还可以在**页面设置**对话框中**布局和路由**选项卡上设置此单元格的值 （**设计**选项卡中，单击**页面设置**箭头，然后单击**布局与排列**）。
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LineJumpFactorY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LineJumpFactorY  <br/> |
   
若要从某个程序按索引获取对 LineJumpFactorY 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLOJumpFactorY** <br/> |
   

