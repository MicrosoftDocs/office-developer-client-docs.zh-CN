---
title: IsSnapTarget 单元格（“Group Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251626
localization_priority: Normal
ms.assetid: b58131f6-a566-d9ca-bad4-4f4b66e03aaf
description: 确定是对齐组合还是对齐该组合内的形状。
ms.openlocfilehash: 89536923617f80768d7c14658cb07c97595824ea
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780495"
---
# <a name="issnaptarget-cell-group-properties-section"></a>IsSnapTarget 单元格（“Group Properties”部分）

确定是对齐组合还是对齐该组合内的形状。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |启用对齐组合内的形状。  <br/> |
|FALSE  <br/> |只对齐组合。  <br/> |
   
## <a name="remarks"></a>注解

您还可以采用以下方法设置此值：选择该组合，在[“开发工具”](run-in-developer-mode-display-the-developer-tab.md)选项卡上单击 **“行为”**，然后选中 **“对齐成员形状”** 复选框。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 IsSnapTarget 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |IsSnapTarget  <br/> |
   
若要从某个程序按索引获取对 IsSnapTarget 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowGroup** <br/> |
|单元格索引：  <br/> |**visGroupIsSnapTarget** <br/> |
   

