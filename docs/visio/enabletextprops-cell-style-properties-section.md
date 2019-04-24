---
title: EnableTextProps 单元格（“Style Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251697
localization_priority: Normal
ms.assetid: 8c59abaf-d2cc-94c9-08ba-004bc40efd9e
description: 确定样式是否包括文本属性。
ms.openlocfilehash: 3f1d87316955b4e6e40cea16634cff7645a720fe
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328915"
---
# <a name="enabletextprops-cell-style-properties-section"></a>EnableTextProps 单元格（“Style Properties”内容）

确定样式是否包括文本属性。
  
|**Value**|**说明**|
|:-----|:-----|
|TRUE  <br/> |包括文本属性。  <br/> |
|FALSE  <br/> |不包括文本属性。  <br/> |
   
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EnableTextProps 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |EnableTextProps  <br/> |
   
要从某个程序按索引获取对 EnableTextProps 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowStyle** <br/> |
|单元格索引：  <br/> |**visStyleIncludesText** <br/> |
   

