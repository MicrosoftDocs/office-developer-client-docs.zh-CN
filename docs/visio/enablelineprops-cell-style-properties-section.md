---
title: EnableLineProps 单元格（“Style Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251696
localization_priority: Normal
ms.assetid: 9f619416-36ff-1479-6232-225c11827e01
description: 确定样式是否包括线条属性。
ms.openlocfilehash: 0e1eb67528b3e87bcfff5281dd1e0b2db3a0a4d5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780173"
---
# <a name="enablelineprops-cell-style-properties-section"></a>EnableLineProps 单元格（“Style Properties”部分）

确定样式是否包括线条属性。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |包括线条属性。  <br/> |
|FALSE  <br/> |不包括线条属性。  <br/> |
   
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EnableLineProps 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |EnableLineProps  <br/> |
   
要从某个程序按索引获取对 EnableLineProps 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowStyle** <br/> |
|单元格索引：  <br/> |**visStyleIncludesLine** <br/> |
   

