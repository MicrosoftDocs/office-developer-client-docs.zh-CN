---
title: ConLineJumpDirX 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm185
localization_priority: Normal
ms.assetid: f0671835-8d48-907a-eca6-43953658f800
description: 确定出现在形状的水平动态连接线上的跨线的方向。
ms.openlocfilehash: 22b9366b750a85a76498b83880aac2b9b974e1ac
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415038"
---
# <a name="conlinejumpdirx-cell-shape-layout-section"></a>ConLineJumpDirX 单元格（“Shape Layout”内容）

确定出现在形状的水平动态连接线上的跨线的方向。
  
|**值**|**跨线方向**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 页面默认值  <br/> |**visLOJumpDirXDefault** <br/> |
| 1  <br/> | 向上  <br/> |**visLOJumpDirXUp** <br/> |
| 双面  <br/> | 向下  <br/> |**visLOJumpDirXDown** <br/> |
   
## <a name="remarks"></a>说明

若要设置页面上*所有*连接线跨线的默认水平方向, 请使用 "页面布局" 部分中的 "PageLineJumpDirX" 单元格。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ConLineJumpDirX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ConLineJumpDirX  <br/> |
   
要从某个程序按索引获取对 ConLineJumpDirX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowShapeLayout** <br/> |
| 单元格索引：  <br/> |**visSLOJumpDirX** <br/> |
   

