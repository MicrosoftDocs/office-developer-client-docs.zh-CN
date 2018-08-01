---
title: ConLineRouteExt 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm50110
localization_priority: Normal
ms.assetid: cafd7589-1c94-b9bc-b1a6-40f7c15fba71
description: 确定连接线的外观。
ms.openlocfilehash: 7724466b6ad225fcf39243bc80ba2e440f3b700b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779956"
---
# <a name="conlinerouteext-cell-shape-layout-section"></a>ConLineRouteExt 单元格（“Shape Layout”部分）

确定连接线的外观。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 默认值；使用页面设置  <br/> |**visLORouteExtDefault** <br/> |
| 1  <br/> | 直线  <br/> |**visLORouteExtStraight** <br/> |
| 2  <br/> | 曲线  <br/> |**visLORouteExtNURBS** <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ConLineRouteExt 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ConLineRouteExt  <br/> |
   
要从某个程序按索引获取对 ConLineRouteExt 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowShapeLayout** <br/> |
| 单元格索引：  <br/> |**visSLOLineRouteExt** <br/> |
   

