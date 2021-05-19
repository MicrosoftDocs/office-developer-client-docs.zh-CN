---
title: LockMoveY 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm645
localization_priority: Normal
ms.assetid: 4ed8cab4-112a-e96a-f4e3-02490a6f87fa
description: 锁定形状的垂直位置，使它不能垂直移动。
ms.openlocfilehash: 6666d47555f8175b4950f95e1fb15abb8b11bfd5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434044"
---
# <a name="lockmovey-cell-protection-section"></a>LockMoveY 单元格（“Protection”内容）

锁定形状的垂直位置，使它不能垂直移动。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 已锁定垂直位置。  <br/> |
| FALSE  <br/> | 未锁定垂直位置。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockMoveY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockMoveY  <br/> |
   
要从某个程序按索引获取对 LockMoveY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockMoveY** <br/> |
   

