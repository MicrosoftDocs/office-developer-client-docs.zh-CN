---
title: LockThemeColors 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm70001
localization_priority: Normal
ms.assetid: 22cedeb3-58b5-3932-9252-5c9dd3e163e3
ms.openlocfilehash: 81091ea33be2158435d240ba14f3c97e8f3fcc39
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348284"
---
# <a name="lockthemecolors-cell-protection-section"></a>LockThemeColors 单元格（“Protection”内容）

阻止将主题颜色应用到形状。 
  
LockThemeColors 单元格的值与 **“保护”** 对话框中的 **“阻止应用主题颜色”** 复选框设置相对应。 
  
若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称引用 LockThemeColors 单元格，请使用：

 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LockThemeColors  <br/> |
   
若要从某个程序按索引引用 LockThemeColors 单元格，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLock** <br/> |
|单元格索引：  <br/> |**visLockThemeColors** <br/> |
   

