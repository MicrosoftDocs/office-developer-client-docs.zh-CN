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
description: 代表 x 的形状的旋转中心点 （旋转中心） 相对于形状的原点坐标。 用于确定 LocPinX 默认公式为：
ms.openlocfilehash: 17f7b0fde9a54f6596f2f87f866d30b908e062b5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780671"
---
# <a name="locpinx-cell-shape-transform-section"></a>LocPinX 单元格（“Shape Transform”部分）

代表*x*的形状的旋转中心点 （旋转中心） 相对于形状的原点坐标。 用于确定 LocPinX 默认公式为： 
  
= 宽度\*0.5
  
## <a name="remarks"></a>说明

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
   

