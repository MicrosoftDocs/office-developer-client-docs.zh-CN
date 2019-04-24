---
title: AlignBottom 单元格（“Alignment”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm20
localization_priority: Normal
ms.assetid: 234e7ffa-04e3-0204-c5be-7ff7a4d0d54c
description: 确定垂直位置，该位置是相对于其父级的原点、形状的下边框依其对齐的水平参考线或辅助点的原点而言的。
ms.openlocfilehash: 66fea9949f2f31eb5c3aaf43804ac0ec9f7e20fe
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346562"
---
# <a name="alignbottom-cell-alignment-section"></a>AlignBottom 单元格（“Alignment”内容）

确定垂直位置，该位置是相对于其父级的原点、形状的下边框依其对齐的水平参考线或辅助点的原点而言的。
  
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 AlignBottom 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | AlignBottom  <br/> |
   
要从某个程序按索引获取对 AlignBottom 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowAlign** <br/> |
| 单元格索引：  <br/> |**visAlignBottom** <br/> |
   

