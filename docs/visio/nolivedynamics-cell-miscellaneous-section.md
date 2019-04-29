---
title: NoLiveDynamics 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm720
localization_priority: Normal
ms.assetid: d1c4b9d9-6d64-8ed1-9fc6-2dbf829a75b5
description: 确定在您操纵一个形状时，该形状是否动态改变大小或旋转。
ms.openlocfilehash: e332546c1fc5dfc71dfa3b72ea5a58bfef59dc7f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421478"
---
# <a name="nolivedynamics-cell-miscellaneous-section"></a>NoLiveDynamics 单元格（“Miscellaneous”内容）

确定在您操纵一个形状时，该形状是否动态改变大小或旋转。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 操纵形状时不动态更新它。  <br/> |
| FALSE  <br/> | 操纵形状时动态更新它。  <br/> |
   
## <a name="remarks"></a>说明

当您调整不具备实时动态的二维 (2-D) 形状的大小或旋转该形状时，您将看到一个选择框。如果是一维 (1-D) 形状，您看到的是基于 DynFeedback 单元格的值的反馈。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NoLiveDynamics 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | NoLiveDynamics  <br/> |
   
要从某个程序按索引获取对 NoLiveDynamics 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowMisc** <br/> |
| 单元格索引：  <br/> |**visNoLiveDynamics** <br/> |
   

