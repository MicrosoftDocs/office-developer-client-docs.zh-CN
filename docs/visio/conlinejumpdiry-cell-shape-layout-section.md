---
title: ConLineJumpDirY 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251654
localization_priority: Normal
ms.assetid: 93f82ae0-3442-fac1-9906-b84afef85f5c
description: 确定出现在形状的垂直动态连接线上的跨线的跨线方向。
ms.openlocfilehash: f86c77da62042d1bc2c0274564efa9fdb0887971
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404769"
---
# <a name="conlinejumpdiry-cell-shape-layout-section"></a>ConLineJumpDirY 单元格（“Shape Layout”内容）

确定出现在形状的垂直动态连接线上的跨线的跨线方向。
  
|**值**|**跨线方向**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 页面默认值  <br/> |**visLOJumpDirYDefault** <br/> |
| 1  <br/> | 左侧  <br/> |**visLOJumpDirYLeft** <br/> |
| 2  <br/> | 右侧  <br/> |**visLOJumpDirYRight** <br/> |
   
## <a name="remarks"></a>备注

若要设置页面上所有连接线跳转的默认垂直方向，请使用"页面布局"部分中的 PageLineJumpDirY 单元格。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ConLineJumpDirY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ConLineJumpDirY  <br/> |
   
要从某个程序按索引获取对 ConLineJumpDirY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowShapeLayout** <br/> |
| 单元格索引：  <br/> |**visSLOJumpDirY** <br/> |
   

