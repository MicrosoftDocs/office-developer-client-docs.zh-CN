---
title: LockRotate 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm655
localization_priority: Normal
ms.assetid: 2d97b31d-9008-307d-273a-1726007eeb34
description: 锁定二维形状，以免它随旋转手柄或者向左旋转 90 ° 或向右旋转 90 ° 命令。
ms.openlocfilehash: 450fe4786594472d018b705df4678fe636390ac3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780638"
---
# <a name="lockrotate-cell-protection-section"></a>LockRotate 单元格（“Protection”内容）

锁定二维形状，以免它随旋转手柄或者**左侧的旋转 90 °**或**右旋转 90 °**命令。 
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 不能旋转形状。  <br/> |
| FALSE  <br/> | 可以旋转形状（默认值）。  <br/> |
   
## <a name="remarks"></a>注解

当拖动一维形状的某个端点时，LockRotate 单元格不能阻止该形状旋转。要锁定一维形状以免其旋转，请将 LockWidth 单元格设置为非零值 (TRUE)。
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LockRotate 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockRotate  <br/> |
   
若要从某个程序按索引获取对 LockRotate 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockRotate** <br/> |
   

