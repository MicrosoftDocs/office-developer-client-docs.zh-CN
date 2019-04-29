---
title: LockVtxEdit 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251224
localization_priority: Normal
ms.assetid: 966cde5c-f04e-7149-3660-720ffa4f7079
description: 锁定形状的顶点，以使它们无法编辑。
ms.openlocfilehash: 1703769fe54171a14f7052f0f6686e1eb5ec92fc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417663"
---
# <a name="lockvtxedit-cell-protection-section"></a>LockVtxEdit 单元格（“Protection”内容）

锁定形状的顶点，以使它们无法编辑。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |不能编辑顶点。  <br/> |
|FALSE  <br/> |能够编辑顶点。  <br/> |
   
## <a name="remarks"></a>说明

若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LockVtxEdit 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LockVtxEdit  <br/> |
   
若要从某个程序按索引获取对 LockVtxEdit 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLock** <br/> |
|单元格索引：  <br/> |**visLockVtxEdit** <br/> |
   

