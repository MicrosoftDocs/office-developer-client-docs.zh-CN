---
title: LocPinX 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm680
localization_priority: Normal
ms.assetid: b82feade-5793-8a6e-3ff4-69a4cbdd2cf9
description: 表示形状的旋转中心点 (旋转中心) 相对于形状原点）的 x 坐标。 确定 LocPinX 的默认公式为：
ms.openlocfilehash: 2eb5c328eed3c97652173670c426b83b8c358833
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439238"
---
# <a name="locpinx-cell-shape-transform-section"></a>LocPinX 单元格（“Shape Transform”内容）

表示形状的旋转中心点 (旋转中心) 相对于形状原点）的  *x*  坐标。 确定 LocPinX 的默认公式为： 
  
= 宽度 \* 0.5
  
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LocPinX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LocPinX  <br/> |
   
要从某个程序按索引获取对 LocPinX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowXFormOut** <br/> |
| 单元格索引：  <br/> |**visXFormLocPinX** <br/> |
   

