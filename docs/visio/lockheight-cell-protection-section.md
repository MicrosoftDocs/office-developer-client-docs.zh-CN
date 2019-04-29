---
title: LockHeight 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm635
localization_priority: Normal
ms.assetid: 218b957e-5af6-e53b-1453-a84164ae456e
description: 锁定形状的高度，以便在调整该形状的大小时使其高度保持不变。
ms.openlocfilehash: 099f6597656d4389476818253f34e741ddd404de
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432084"
---
# <a name="lockheight-cell-protection-section"></a>LockHeight 单元格（“Protection”内容）

锁定形状的高度，以便在调整该形状的大小时使其高度保持不变。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 已锁定高度。  <br/> |
| FALSE  <br/> | 未锁定高度。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockHeight 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockHeight  <br/> |
   
要从某个程序按索引获取对 LockHeight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockHeight** <br/> |
   

