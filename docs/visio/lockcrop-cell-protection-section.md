---
title: LockCrop 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm610
localization_priority: Normal
ms.assetid: ae05de63-b527-66e6-2c79-056c9c92ec95
description: 锁定来自其他程序的对象，防止它被“剪裁”工具剪裁。
ms.openlocfilehash: bfb8bebd50908387fa3f94a8ca228935ef709133
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411853"
---
# <a name="lockcrop-cell-protection-section"></a>LockCrop 单元格（“Protection”内容）

锁定来自其他程序的对象，防止它被 **“剪裁”** 工具剪裁。 
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 不能剪裁形状  <br/> |
| FALSE  <br/> | 能够剪裁形状。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockCrop 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockCrop  <br/> |
   
要从某个程序按索引获取对 LockCrop 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockCrop** <br/> |
   

