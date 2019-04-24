---
title: PageLineJumpDirY 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm770
localization_priority: Normal
ms.assetid: f73cc157-b332-279b-f7cf-d5a090bc09a4
description: 确定在尚未应用本地跨线方向的绘图页内垂直动态连接线上的跨线方向。
ms.openlocfilehash: 21ad1d95fd83780f31778dbc8bb70f9bdb4b922d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329895"
---
# <a name="pagelinejumpdiry-cell-page-layout-section"></a>PageLineJumpDirY 单元格（“Page Layout”内容）

确定在尚未应用本地跨线方向的绘图页内垂直动态连接线上的跨线方向。
  
|**值**|**跨线方向**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 默认值；向上或形状的页面设置  <br/> |**visLOJumpDirYDefault** <br/> |
| 1  <br/> | 左侧  <br/> |**visLOJumpDirYLeft** <br/> |
| 双面  <br/> | 右侧  <br/> |**visLOJumpDirYRight** <br/> |
   
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PageLineJumpDirY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | PageLineJumpDirY  <br/> |
   
要从某个程序按索引获取对 PageLineJumpDirY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPageLayout** <br/> |
| 单元格索引：  <br/> |**visPLOJumpDirY** <br/> |
   

