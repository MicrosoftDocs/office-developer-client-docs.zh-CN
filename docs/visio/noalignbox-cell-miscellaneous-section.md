---
title: NoAlignBox 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm700
localization_priority: Normal
ms.assetid: b2d51f4b-d64e-fd14-4ff1-ed67c69213bc
description: 切换选中形状的选择矩形的显示状态 - 显示或不显示。
ms.openlocfilehash: 2ff9f051df54f4d424589332b9fbaea973552edc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435878"
---
# <a name="noalignbox-cell-miscellaneous-section"></a>NoAlignBox 单元格（“Miscellaneous”内容）

切换选中形状的选择矩形的显示状态 - 显示或不显示。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 选中形状后不显示选择矩形。  <br/> |
| FALSE  <br/> | 选中形状后显示选择矩形。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NoAlignBox 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | NoAlignBox  <br/> |
   
要从某个程序按索引获取对 NoAlignBox 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowMisc** <br/> |
| 单元格索引：  <br/> |**visNoAlignBox** <br/> |
   

