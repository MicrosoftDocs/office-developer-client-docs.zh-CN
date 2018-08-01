---
title: LineRouteExt 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm50115
localization_priority: Normal
ms.assetid: 3d16b8b3-601b-c10b-68a8-ffd47251306f
description: 确定绘图页上所有连接线的默认外观。
ms.openlocfilehash: 21da283f2d9ab43837b8fe4127840e89ea9d9949
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780593"
---
# <a name="linerouteext-cell-page-layout-section"></a>LineRouteExt 单元格（“Page Layout”部分）

确定绘图页上所有连接线的默认外观。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 默认值（直线）  <br/> |**visLORouteExtDefault** <br/> |
| 1  <br/> | 直线  <br/> |**visLORouteExtStraight** <br/> |
| 2  <br/> | 曲线  <br/> |**visLORouteExtNURBS** <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LineRouteExt 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LineRouteExt  <br/> |
   
要从某个程序按索引获取对 LineRouteExt 单元格的引用，请使用带下列参数的  **CellsSRC**  属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPageLayout** <br/> |
| 单元格索引：  <br/> |**visPLOLineRouteExt** <br/> |
   

