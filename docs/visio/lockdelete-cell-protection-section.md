---
title: LockDelete 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251219
localization_priority: Normal
ms.assetid: 596c62b7-8d42-1854-d709-592db09a6a84
description: 锁定形状，使它不能被删除。
ms.openlocfilehash: 00229dcabf45d2a3435039ffe05fd7eb4de75808
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780620"
---
# <a name="lockdelete-cell-protection-section"></a>LockDelete 单元格（“Protection”部分）

锁定形状，使它不能被删除。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 不能删除形状  <br/> |
| FALSE  <br/> | 能够删除形状。  <br/> |
   
## <a name="remarks"></a>注释

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockDelete 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockDelete  <br/> |
   
要从某个程序按索引获取对 LockDelete 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockDelete** <br/> |
   

