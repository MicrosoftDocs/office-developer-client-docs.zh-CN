---
title: LockAspect 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251218
localization_priority: Normal
ms.assetid: e9bfced5-af29-f86c-8604-44ec9a573229
description: 锁定形状的纵横比，使形状只能按比例调整大小，而不能单维度调整大小。
ms.openlocfilehash: 83ce1aaf555cfaaa0109423e74ae930450b4c1e2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359638"
---
# <a name="lockaspect-cell-protection-section"></a>LockAspect 单元格（“Protection”内容）

锁定形状的纵横比，使形状只能按比例调整大小，而不能单维度调整大小。
  
|**Value**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 已锁定纵横比。  <br/> |
| FALSE  <br/> | 未锁定纵横比。  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LockAspect 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockAspect  <br/> |
   
若要从某个程序按索引获取对 LockAspect 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockAspect** <br/> |
   

