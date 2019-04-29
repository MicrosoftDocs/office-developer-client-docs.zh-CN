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
ms.openlocfilehash: 38964194626be052b2a168fa929b69ebe4b28e01
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409998"
---
# <a name="enablelineprops-cell-style-properties-section"></a>EnableLineProps 单元格（“Style Properties”内容）

确定样式是否包括线条属性。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |包括线条属性。  <br/> |
|FALSE  <br/> |不包括线条属性。  <br/> |
   
## <a name="remarks"></a>说明

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
   

