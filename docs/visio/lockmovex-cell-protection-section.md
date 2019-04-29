---
title: LockMoveX 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm640
localization_priority: Normal
ms.assetid: 48ceeeed-66ae-a81f-2aee-f0010102dfb7
description: 锁定形状的水平位置，使它不能水平移动。
ms.openlocfilehash: af0cee32370a540cd8d7aaf960cc0cbc27cc8f97
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435857"
---
# <a name="lockmovex-cell-protection-section"></a>LockMoveX 单元格（“Protection”内容）

锁定形状的水平位置，使它不能水平移动。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 已锁定水平位置。  <br/> |
| FALSE  <br/> | 未锁定水平位置。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockMoveX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockMoveX  <br/> |
   
要从某个程序按索引获取对 LockMoveX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockMoveX** <br/> |
   

