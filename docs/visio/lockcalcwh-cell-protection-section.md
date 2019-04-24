---
title: LockCalcWH 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm605
localization_priority: Normal
ms.assetid: 6eb51e5a-03d8-3daa-b4e1-6107d540aed9
description: 锁定形状的选择矩形，使得在“Geometry”内容中编辑顶点或更改行类型时，不会重新计算选择矩形。
ms.openlocfilehash: 2b1d907f480a22a56f5847035da8d1cbde5fdcc5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359631"
---
# <a name="lockcalcwh-cell-protection-section"></a>LockCalcWH 单元格（“Protection”内容）

锁定形状的选择矩形，使得在“Geometry”内容中编辑顶点或更改行类型时，不会重新计算选择矩形。
  
|**Value**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 不能重新计算宽度和高度。  <br/> |
| FALSE  <br/> | 能够重新计算宽度和高度。  <br/> |
   
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockCalcWH 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockCalcWH  <br/> |
   
要从某个程序按索引获取对 LockCalcWH 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockCalcWH** <br/> |
   

