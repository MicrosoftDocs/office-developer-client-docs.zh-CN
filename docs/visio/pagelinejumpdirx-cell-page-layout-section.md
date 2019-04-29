---
title: PageLineJumpDirX 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251656
localization_priority: Normal
ms.assetid: 77892ec7-4c6a-78a5-5af4-5b6be7709e77
description: 确定在尚未应用本地跨线方向的绘图页内水平动态连接线上的跨线方向。
ms.openlocfilehash: 4e1213990877e1260cc8cecd5a55beda4592a844
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431006"
---
# <a name="pagelinejumpdirx-cell-page-layout-section"></a>PageLineJumpDirX 单元格（“Page Layout”内容）

确定在尚未应用本地跨线方向的绘图页内水平动态连接线上的跨线方向。
  
|**值**|**跨线方向**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 默认值；向左或形状的页面设置  <br/> |**visLOJumpDirXDefault** <br/> |
| 1  <br/> | 向上  <br/> |**visLOJumpDirXUp** <br/> |
| 双面  <br/> | 向下  <br/> |**visLOJumpDirXDown** <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PageLineJumpDirX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | PageLineJumpDirX  <br/> |
   
要从某个程序按索引获取对 PageLineJumpDirX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPageLayout** <br/> |
| 单元格索引：  <br/> |**visPLOJumpDirX** <br/> |
   

