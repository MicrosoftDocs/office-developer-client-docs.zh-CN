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
ms.openlocfilehash: c8e5fe28197a72b4cdb5306732dd155dc8f4f810
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780785"
---
# <a name="noalignbox-cell-miscellaneous-section"></a>NoAlignBox 单元格（“Miscellaneous”部分）

切换选中形状的选择矩形的显示状态 - 显示或不显示。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 选中形状后不显示选择矩形。  <br/> |
| FALSE  <br/> | 选中形状后显示选择矩形。  <br/> |
   
## <a name="remarks"></a>注解

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
   

