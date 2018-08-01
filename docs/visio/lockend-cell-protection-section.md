---
title: LockEnd 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm620
localization_priority: Normal
ms.assetid: e9742142-4d34-1ba9-480e-d1ecff4fc7cd
description: 将一维形状的终点 (EndX, EndY) 锁定在特定位置上。
ms.openlocfilehash: d29f07e5b4b77ed2fb8b104769a2fdca55abcc8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780623"
---
# <a name="lockend-cell-protection-section"></a>LockEnd 单元格（“Protection”部分）

将一维形状的终点 (EndX, EndY) 锁定在特定位置上。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 已锁定终点。  <br/> |
| FALSE  <br/> | 未锁定终点。  <br/> |
   
## <a name="remarks"></a>注释

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockEnd 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockEnd  <br/> |
   
要从某个程序按索引获取对 LockEnd 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockEnd** <br/> |
   

