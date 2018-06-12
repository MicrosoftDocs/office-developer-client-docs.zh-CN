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
ms.openlocfilehash: f6afe6037ff3d0810cc532bbc18bb749ee589bb1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780629"
---
# <a name="lockheight-cell-protection-section"></a>LockHeight 单元格（“Protection”内容）

锁定形状的高度，以便在调整该形状的大小时使其高度保持不变。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 已锁定高度。  <br/> |
| FALSE  <br/> | 未锁定高度。  <br/> |
   
## <a name="remarks"></a>注释

要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LockHeight 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockHeight  <br/> |
   
若要从某个程序按索引获取对 LockHeight 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockHeight** <br/> |
   

