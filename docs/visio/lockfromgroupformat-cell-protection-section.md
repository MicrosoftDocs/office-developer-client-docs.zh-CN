---
title: LockFromGroupFormat 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: abd175af-ad4e-b84a-2687-2c9358653499
ms.openlocfilehash: 3daeb4704a33ba836cf82c9ab3517c6ca6be8db7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359589"
---
# <a name="lockfromgroupformat-cell-protection-section"></a>LockFromGroupFormat 单元格（“Protection”内容）

阻止将组形状的格式更改传播到其子形状, 同时仍允许用户直接设置选定子形状的格式。 
  
LockFromGroupFormat 单元格的值与 **“保护”** 对话框中的 **“阻止应用组格式”** 复选框设置相对应。 
  
若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称引用 LockFromGroupFormat 单元格，请使用：

 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LockFromGroupFormat  <br/> |
   
若要从某个程序按索引引用 LockFromGroupFormat 单元格，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLock** <br/> |
|单元格索引：  <br/> |**visLockFromGroupFormat** <br/> |
   
该单元格的默认值为 0 (False)。
  

