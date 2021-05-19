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
ms.openlocfilehash: c9f762f390dbea1e4ff2bd5bcf9566b8c67df11f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409753"
---
# <a name="lockselect-cell-protection-section"></a>LockSelect 单元格（“Protection”内容）

防止选取某个形状。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 不能选取形状。  <br/> |
| FALSE  <br/> | 能够选取形状。  <br/> |
   
## <a name="remarks"></a>备注

要使 LockSelect 生效，必须在 **“保护文档”** 对话框中选取 **“形状”** 复选框。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockSelect 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockSelect  <br/> |
   
要从某个程序按索引获取对 LockSelect 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockSelect** <br/> |
   

