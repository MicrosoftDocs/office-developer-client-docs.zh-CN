---
title: LockSelect 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm660
localization_priority: Normal
ms.assetid: c96b45a5-719e-8c4b-71b9-cb2224d83e21
description: 防止选取某个形状。
ms.openlocfilehash: 082e993f7773640f59022c46458563d491197908
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19780649"
---
# <a name="lockselect-cell-protection-section"></a>LockSelect 单元格（“Protection”内容）

防止选取某个形状。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 不能选取形状。  <br/> |
| FALSE  <br/> | 能够选取形状。  <br/> |
   
## <a name="remarks"></a>注释

为了使 LockSelect 生效，必须在**保护文档**对话框中选择**形状**复选框。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LockSelect 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockSelect  <br/> |
   
若要从某个程序按索引获取对 LockSelect 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockSelect** <br/> |
   

