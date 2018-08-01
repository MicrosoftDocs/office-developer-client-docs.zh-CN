---
title: LockGroup 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251227
localization_priority: Normal
ms.assetid: 04b0fa5b-1680-cfe2-6aaf-0502ad196027
description: 锁定某组，使该组不能被取消组合。
ms.openlocfilehash: 4d09d514a3fff8ada40c67eb9cd9537539a1039a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19780642"
---
# <a name="lockgroup-cell-protection-section"></a>LockGroup 单元格（“Protection”部分）

锁定某组，使该组不能被取消组合。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |不能取消组合。  <br/> |
|FALSE  <br/> |能够取消组合。  <br/> |
   
## <a name="remarks"></a>注解

将 LockGroupCell 值设置为 TRUE 还可防止删除作为组合成员的任何形状。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LockGroup 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LockGroup  <br/> |
   
若要从某个程序按索引获取对 LockGroup 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLock** <br/> |
|单元格索引：  <br/> |**visLockGroup** <br/> |
   

