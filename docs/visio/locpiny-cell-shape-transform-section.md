---
title: LocPinY 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm685
localization_priority: Normal
ms.assetid: a29c5d4e-d3d6-d984-495a-4b0b130352ef
description: 代表 y-形状的旋转中心点 （旋转中心） 相对于形状的原点坐标。 用于确定 LocPinY 默认公式为：
ms.openlocfilehash: 8d98906e8082af0fc54bc01fe3a8537b66ac56b8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780658"
---
# <a name="locpiny-cell-shape-transform-section"></a>LocPinY 单元格（“Shape Transform”内容）

代表*y* -形状的旋转中心点 （旋转中心） 相对于形状的原点坐标。 用于确定 LocPinY 默认公式为： 
  
= 高度\*0.5
  
## <a name="remarks"></a>备注

要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LocPinY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LocPinY  <br/> |
   
若要从某个程序按索引获取对 LocPinY 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowXFormOut** <br/> |
| 单元格索引：  <br/> |**visXFormLocPinY** <br/> |
   

