---
title: LockFormat 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm625
localization_priority: Normal
ms.assetid: e9a640f4-0af0-317c-b77b-f32c651e87b4
description: 锁定形状的格式，使它无法更改。
ms.openlocfilehash: e0d1bb8a65b8087136e57bb46ad9f5363da30030
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359611"
---
# <a name="lockformat-cell-protection-section"></a>LockFormat 单元格（“Protection”内容）

锁定形状的格式，使它无法更改。
  
|**Value**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 不能更改格式。  <br/> |
| FALSE  <br/> | 能够更改格式。  <br/> |
   
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockFormat 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockFormat  <br/> |
   
要从某个程序按索引获取对 LockFormat 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockFormat** <br/> |
   

