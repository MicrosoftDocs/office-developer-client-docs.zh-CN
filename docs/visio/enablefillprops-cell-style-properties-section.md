---
title: EnableFillProps 单元格（“Style Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm300
localization_priority: Normal
ms.assetid: 2b3334de-588c-6cf3-bc88-be03ae71b1a6
description: 确定样式是否包括填充属性。
ms.openlocfilehash: 55191cb28d5777f7fb65a3a1e4be890e6dda4e8b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406008"
---
# <a name="enablefillprops-cell-style-properties-section"></a>EnableFillProps 单元格（“Style Properties”内容）

确定样式是否包括填充属性。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |包括填充属性。  <br/> |
|FALSE  <br/> |不包括填充属性。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EnableFillProps 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |EnableFillProps  <br/> |
   
要从某个程序按索引获取对 EnableFillProps 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowStyle** <br/> |
|单元格索引：  <br/> |**visStyleIncludesFill** <br/> |
   

