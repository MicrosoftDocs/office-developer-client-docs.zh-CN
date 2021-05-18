---
title: LockBegin 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm600
localization_priority: Normal
ms.assetid: cce34aba-caae-51ee-992e-92a490b68ea5
description: 将一维形状的起点 (BeginX, BeginY) 锁定在特定位置上。
ms.openlocfilehash: 2e6c6284ff82a88677eb46bb13b8ab8afa986584
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407758"
---
# <a name="lockbegin-cell-protection-section"></a>LockBegin 单元格（“Protection”内容）

将一维形状的起点 (BeginX, BeginY) 锁定在特定位置上。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 已锁定起点。  <br/> |
| FALSE  <br/> | 未锁定起点。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockBegin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockBegin  <br/> |
   
要从某个程序按索引获取对 LockBegin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockBegin** <br/> |
   

