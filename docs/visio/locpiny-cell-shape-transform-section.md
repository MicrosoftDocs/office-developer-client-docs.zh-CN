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
description: 表示形状的旋转中心点相对于 (原) 旋转中心位置的 y 坐标。 确定 LocPinY 的默认公式为：
ms.openlocfilehash: e65bfec8fdcf2be1ee92c23b7afcb183c95ea9fe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410593"
---
# <a name="locpiny-cell-shape-transform-section"></a>LocPinY 单元格（“Shape Transform”内容）

表示形状的旋转中心点 (旋转中心) 相对于形状原点之间的  *y*  坐标。 确定 LocPinY 的默认公式为： 
  
= 高度 \* 0.5
  
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LocPinY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LocPinY  <br/> |
   
要从某个程序按索引获取对 LocPinY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowXFormOut** <br/> |
| 单元格索引：  <br/> |**visXFormLocPinY** <br/> |
   

